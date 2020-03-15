
  

# Attribute Input Component - Input with ability to add user attribute

  

  

## Features

-  [x] Options for different layout: Auto Expanding(Default), Inline, and Fixed Height
-  [x] Opens attributes list at Attribute text position by: Click Or Keyboard navigation at Attribute Text
-  [x] When typing **{{** Add first Attribute from Attributes List and opens Attributes List
-  [x] User can paste attribute text surronded with **{{}}** and it will be recognized by the input
-  [x] Validate that the text between **{{}}** is a user attribute
-  [x] Input value emits after stop writing by 0.5 seconds

  

## API

### Inputs

| Input | Type | Default | Required | Description |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| inputText | string | `''` | Yes| Input initial text |
| configs | [AttributeInputConfigs](#configs) | AttributeInputConfigs class has it's default values | Yes | Input layout and attributes [See More](#configs) |

  

#### configs

**AttributeInputConfigs**: Options for customizing input styles and behavior (located inside attribute-input.service)

    export class AttributeInputConfigs {
	    placeholder: string;
	    maxLength: number;
	    isOneLineInput: boolean;
	    isHeightFixed: boolean;
	    maxHeight: number;
	    fontSize: number;
    }

| Property | Type | Default | Required | Description |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| placeholder| string | `'Text (reqiured)'` | No | Input placeholder text |
| maxLength | number| 360 | No | input text maximum length |
| isOneLineInput | boolean | False | No | Input behaves like one line input as in `<input>` |
| isHeightFixed | boolean | False | No | Input behaves like multiple lines area as in `<textarea>` but the height doesn't change according to text length|
| maxHeight | number | 200 | No | Input maximum height |
| fontSize | number | `14 or 16` | No | Input font-size in **pixels** Default = 14px IF isOneLineInput = true Else 16px |

  

------------------------------------------------

### Outputs


| Output | Type | Description |
| ------------- | ------------- | ------------- |
| (input_edited) | string | Fired when input text edited Or Text attribute edited (RESLECT from attributes list, ADD, DELETE) and emits input value after edit|
| (input_focused) | boolean | Fired when input focused Or blured Event value will be `true` if the input is focused, `false` if blured |
