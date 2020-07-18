 import React, { Component } from 'react';
import './App.css';

import { CustomDropdown } from './customdropdown'
const countryOptions = [
	{ key: 'af', value: 'af', flag: 'af', text: 'Afghanistan' },
	{ key: 'ax', value: 'ax', flag: 'ax', text: 'Aland Islands' },
	{ key: 'al', value: 'al', flag: 'al', text: 'Albania' },
	{ key: 'dz', value: 'dz', flag: 'dz', text: 'Algeria' },
	{ key: 'as', value: 'as', flag: 'as', text: 'American Samoa' },
	{ key: 'ad', value: 'ad', flag: 'ad', text: 'Andorra' },
	{ key: 'ao', value: 'ao', flag: 'ao', text: 'Angola' },
	{ key: 'ai', value: 'ai', flag: 'ai', text: 'Anguilla' },
	{ key: 'ag', value: 'ag', flag: 'ag', text: 'Antigua' },
	{ key: 'ar', value: 'ar', flag: 'ar', text: 'Argentina' },
	{ key: 'am', value: 'am', flag: 'am', text: 'Armenia' },
	{ key: 'aw', value: 'aw', flag: 'aw', text: 'Aruba' },
	{ key: 'au', value: 'au', flag: 'au', text: 'Australia' },
	{ key: 'at', value: 'at', flag: 'at', text: 'Austria' },
	{ key: 'az', value: 'az', flag: 'az', text: 'Azerbaijan' },
	{ key: 'bs', value: 'bs', flag: 'bs', text: 'Bahamas' },
	{ key: 'bh', value: 'bh', flag: 'bh', text: 'Bahrain' },
	{ key: 'bd', value: 'bd', flag: 'bd', text: 'Bangladesh' },
	{ key: 'bb', value: 'bb', flag: 'bb', text: 'Barbados' },
	{ key: 'by', value: 'by', flag: 'by', text: 'Belarus' },
	{ key: 'be', value: 'be', flag: 'be', text: 'Belgium' },
	{ key: 'bz', value: 'bz', flag: 'bz', text: 'Belize' },
	{ key: 'bj', value: 'bj', flag: 'bj', text: 'Benin' },
]

class App extends Component {
	
	render() {
		return (
					<CustomDropdown  countryOptions={countryOptions} />
		);
	}
}

export default App;
import React from "react";
import faker from 'faker'
import _ from 'lodash'
import { Dropdown } from 'semantic-ui-react'
import 'semantic-ui-css/semantic.min.css';
import './dropdown.css';

export function CustomDropdown(props) {
	const handleChange = (e) =>{
		console.log(e.target.innerText)
	}
	const handleAddition = (e) =>{
		console.log(e.target.innerText);
		props.countryOptions.push(
			{ key: e.target.innerText.slice(0,2), value: e.target.innerText.slice(0,2), flag: e.target.innerText.slice(0,2), text: e.target.innerText }
		)
		console.log(props.countryOptions);
	}
	return (
		<div>
			<Dropdown
				placeholder='Select Country'
				clearable multiple
				fluid
				search
				selection
				options={props.countryOptions}
				allowAdditions
				onAddItem={handleAddition}
				onChange={handleChange}

			/>
		</div>
	);
}
