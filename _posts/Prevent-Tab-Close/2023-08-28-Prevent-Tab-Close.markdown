---
layout: post
title:  "Prevent Tab Close"
categories: jekyll update
---
## Description

In web accessibility, the term <b>prevent tab close</b> typically refers to a design or development practice that aims to prevent accidental closure of a tab or window when a user interacts with a web application. This practice is especially important for users who rely on keyboard navigation and screen readers, as they may inadvertently close a tab or window if they press certain keyboard shortcuts or perform certain actions.

## Instructions
Please enter some text in one of the fields below and close the Browser tab or window. 

## Expectations

If any unsaved contents are available, the application should ask the user what to do and not simply lose the data.

## Example

<div>
<style>
  fieldset {
}
h1 {
    font-size: 125%;
}
    h1 span {}
h2 {
    font-size: 110%;
}
h3 {
    font-size: 100%;
}
a {
    color: var(--color-link);
}
button {
    font-size: 100%;
    padding: .25rem;
}
.mb-2 {
    margin-bottom: 1%;
}
</style>
	<form>
			<fieldset>
				<legend>Login Form Example</legend>
				<label for="emailAddress">Email</label>
				<br>
				<input type="text" name="Email" id="emailAddress" class="mb-2" aria-label="Enter your email address">
				<br>
				<label for="passwordInput">Password</label>
				<br>
				<input type="password" name="password" id="passwordInput" class="mb-2" aria-label="Enter your password">
				<br>
				<input type="checkbox" name="checkbox" id="checkbox" class="mb-2">
				<label for="checkbox">Do you agree?</label>
				<br>
				<button type="submit" >Login</button>
			</fieldset>
		</form>
    <script>const beforeUnloadListener = (event) => {
	event.preventDefault();
	return event.returnValue = "";
};
const nameInput = document.querySelector("#emailAddress");
nameInput.addEventListener("input", (event) => {
	if (event.target.value !== "") {
		addEventListener("beforeunload", beforeUnloadListener, {capture: true});
	} else {
		removeEventListener("beforeunload", beforeUnloadListener, {capture: true});
	}
});
const passwordInput = document.querySelector("#passwordInput");
passwordInput.addEventListener("input", (event) => {
	if (event.target.value !== "") {
		addEventListener("beforeunload", beforeUnloadListener, {capture: true});
	} else {
		removeEventListener("beforeunload", beforeUnloadListener, {capture: true});
	}
});
</script>
 </div>