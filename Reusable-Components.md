# Reusable Components

- F.I.R.S.T. Focused, Independent, Small, and Testable components are well suited to creating larger complex components because they are 'Reusable'.

![alt resusable-components] (atomic-design.png)
- Atoms:
smallest building blocks of an application.
text inputs, labels (for inputs), buttons, progress indicators, links, and so on.
- Molecules:
With atomic components, we can combine these customized atoms into molecules and layer functionality on top.
We'll use a <Label /> component to build a <TextInput />, and then use that to build a <PasswordInput />.
- Organisms:
collection of molecules that function together to make a complete piece of user interface work.
building is a form out of our molecular components <TextInput /> and <PasswordInput />
