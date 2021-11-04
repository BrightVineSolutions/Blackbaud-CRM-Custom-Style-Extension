# Blackbaud-CRM-Custom-Style-Extension
 A Blackbaud CRM plugin that allows for the UI style to be overridden with CSS and JavaScript.

## Deployment
1. Deploy the bin and browser folders to the CRM application server by copying them into the vroot folder on the server.

1. Open **vroot\browser\brand\current\brandoptions.xml** 
and change this:


    ```
    <WebShellPluginAssembly>Blackbaud.AppFx.BBEC.WebUI</WebShellPluginAssembly>
    ```

    to this:
    
    ```
    <WebShellPluginAssembly>Blackbaud.CustomFx.WebShellPluginGeneralCSS.WebUI</WebShellPluginAssembly>
    ```
1. Recycle your AppPool

## Development Steps
1. Make your desired CRM styling changes to the sass file named **skin-combo-min.scss** in a code editor such as [Visual Studio Code](https://code.visualstudio.com/) or [Atom](https://atom.io/). 

1. Run a scss > css translation tool (like [Live Sass Compiler](https://github.com/ritwickdey/vscode-live-sass-compiler) Visual Studio Code extension) to generate an updated version of the **skin-combo-min.css** file. 

1. Your styling updates should now be reflected in the CRM environment through **skin-combo-min.css**.

## Tips
1. You can base64 embed fonts (taken from client websites) using [transfonter](https://transfonter.org/) directly into the sass.

1. Same thing for images using [base64-image](https://www.base64-image.de/)

1. Changing the font system-wide can be challenging. Here is a style to help change the default font size:
 
```
// Code to get started with font resizing
.bbui-skin-webshell, .bbui-skin-webshell table, .bbui-skin-webshell input, .bbui-skin-webshell .x-grid3-hd-row td, .bbui-skin-webshell .x-grid3-row td, .bbui-skin-webshell .x-grid3-summary-row td, .bbui-skin-webshell .x-combo-list, .bbui-skin-webshell .x-toolbar .x-btn button, .bbui-skin-webshell .x-menu-list-item, .bbui-skin-webshell .x-tree-node, .bbui-skin-webshell .x-list-body dt em, .bbui-skin-webshell .x-list-header-inner div em, .bbui-skin-webshell .x-tab-strip span.x-tab-strip-text, .bbui-skin-webshell .x-panel-header, .bbui-skin-webshell .x-btn button, .bbui-skin-webshell .dhx_cal_container, .bbui-skin-webshell .x-tip .x-tip-body, .bbui-skin-webshell .x-window-mc, .bbui-skin-webshell .x-grid-group-hd div.x-grid-group-title, .bbui-skin-webshell .x-toolbar td, .bbui-skin-webshell .x-toolbar span, .bbui-skin-webshell .x-toolbar input, .bbui-skin-webshell .x-toolbar div, .bbui-skin-webshell .x-toolbar select, .bbui-skin-webshell .x-toolbar label, .bbui-skin-webshell .x-panel-fbar td, .bbui-skin-webshell .x-panel-fbar span, .bbui-skin-webshell .x-panel-fbar input, .bbui-skin-webshell .x-panel-fbar div, .bbui-skin-webshell .x-panel-fbar select, .bbui-skin-webshell .x-panel-fbar label, .bbui-skin-webshell .x-window-header-text {
   font-size: 14px;
}
```