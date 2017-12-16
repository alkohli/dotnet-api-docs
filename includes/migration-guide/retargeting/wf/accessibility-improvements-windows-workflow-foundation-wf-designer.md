### Accessibility improvements in Windows Workflow Foundation (WF) workflow designer

|   |   |
|---|---|
|Details|The Windows Workflow Foundation (WF) workflow designer is improving how it works with accessibility technologies. These improvements include the following changes:<ul><li>The tab order is changed to left to right and top to bottom in some controls:</li><li>The initialize correlation window for setting correlation data for the <xref:System.ServiceModel.Activities.InitializeCorrelation> activity</li><li>The content definition window for the <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply> activities</li><li>More functions are available via the keyboard:</li><li>When editing the properties of an activity, property groups can be collapsed by keyboard the first time they are focused.</li><li>Warning icons are now accessible by keyboard.</li><li>The More Properties button in the Properties window is now accessible by keyboard.</li><li>Keyboard users now can access the header items in the Arguments and Variables panes of the Workflow Designer.</li><li>Improved visibility of items with focus, such as when:</li><li>Adding rows to data grids used by the Workflow Designer and activity designers.</li><li>Tabbing through fields in the <xref:System.ServiceModel.Activities.ReceiveReply> and <xref:System.ServiceModel.Activities.SendReply> activities.</li><li>Setting default values for variables or arguments</li><li>Screen readers can now correctly recognize:</li><li>Breakpoints set in the workflow designer.</li><li>The <xref:System.Activities.Statements.FlowSwitch>, <xref:System.Activities.Statements.FlowDecision>, and <xref:System.ServiceModel.Activities.CorrelationScope> activities.</li><li>The contents of the <xref:System.ServiceModel.Activities.Receive> activity.</li><li>The Target Type for the <xref:System.Activities.Statements.InvokeMethod> activity.</li><li>The Exception combo box and the Finally section in the <xref:System.Activities.Statements.TryCatch> activity.</li><li>The Message Type combobox, the splitter in the Add Correlation Initializers window, the Content Definition window, and the CorrelatesOn Defintion window in the messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.SendReply>, and <xref:System.ServiceModel.Activities.ReceiveReply>).</li><li>State machine transitions and transitions destinations.</li><li>Annotations and connectors on <xref:System.Activities.Statements.FlowDecision> activities.</li><li>The context (right-click) menus for activities.</li><li>The property value editors, the Clear Search button, the By Category and Alphabetical sort buttons, and the Expression Editor dialog in the properties grid.</li><li>The zoom percentage in the Workflow Designer.</li><li>The separator in <xref:System.Activities.Statements.Parallel> and <xref:System.Activities.Statements.Pick> activities.</li><li>The <xref:System.Activities.Statements.InvokeDelegate> activity.</li><li>The Select Types window for dictionary activities (<xref:Microsoft.Activities.AddToDictionary>, <xref:Microsoft.Activities.RemoveFromDictionary>, etc.).</li><li>The Browse and Select .NET Type window.</li><li>Breadcrumbs in the Workflow Designer.</li><li>Users who choose High Contrast themes will see many improvements in the visibility of the Workflow Designer and its controls like better contrast ratios between elements and more noticeable selection boxes used for focus elements.</li></ul>|
|Suggestion|If you have an application with a re-hosted workflow designer, your application can benefit from these changes by performing either of these actions:<ul><li>Recompile your application to target the .NET Framework 4.7.1. These accessibility changes are enabled by default.</li><li>If your application targets the .NET Framework 4.7 or earlier but is running on the .NET Framework 4.7.1, you can opt out of these legacy accessibility behaviors by adding the following [AppContext switch](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) to the <code>&lt;runtime&gt;</code> section of the app.config file and set it to <code>false</code>, as the following example shows.</li></ul><pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true|false;key2=true|false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to <code>true</code>.|
|Scope|Minor|
|Version|4.7.1|
|Type|Retargeting|
