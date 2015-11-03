# angular Factories_Services_Providers


## create simple directive

Lets start slow by just creating a simple directive and understanding a little bit about the restrict and template fields.

restrict – The restrict option is typically set to:
```javascript
  .directive('myCustomer', function() {
    return {
      restrict: 'E',
      templateUrl: 'my-customer.html'
    };
  })
```
* 'A' - only matches attribute name
* 'E' - only matches element name
* 'C' - only matches class name
* 'AEC' - matches either attribute or element or class name
template – This specifies the HTML markup that will be produced when the directive is compiled and linked by Angular. 
```javascript
  .directive('myCustomer', function() {
    return {
      template: 'Name: {{customer.name}} Address: {{customer.address}}'
    };
  });
```

You can also use templateUrl
```javascript
  .directive('myCustomer', function() {
    return {
      templateUrl: 'my-customer.html'
    };
  });
```
Check out this [GIST simple directive](https://gist.github.com/GreenPioneer/0427980713a6ae817642). It shows at a baseline of how a directive can work for you. 

Next Step: Now lets start building your jsfiddle directive. Give it a name , a template with a table and these 5 fields:<th>Name</th>
,<th>Created</th>,<th>Description</th>,<th>Latest Version</th>&<th>View</th>.

## Replace ng-controller with Component Directive

You have an ng-controller somewhere other than the root of a template. This is a good sign that there might be a component hiding here.

ng-controller often demarcates an area of the template that's somehow independent, or separate from its parents and siblings. If it is, it should be a component.

Check out this [GIST to replace ng-controller](https://gist.github.com/GreenPioneer/d3f54443e50e5369bc64)

Next Step: Take out your logic for the jsfiddle directive and create one for itself and inject it into the directive. You can leave a main controller on the page for now to inject content later. We will be by the end completely taking out the ng-controller tag.

## Move Markup to Component Template

You have a component directive with a controller. In the child nodes of the component element there are expressions that use the component controller. This is most often the case right after you've applied Replace ng-controller with Component Directive. So lets clean up the html and place it into a templateUrl if you havent done so already. Should look something like this [GIST replace html - template](https://gist.github.com/GreenPioneer/7e19b78bfcaf3719d636)

Next Step:Take your html in your template and place it into its own file and reference it to the TemplateUrl.

## Wrap Markup in Component Directive 


You have a big template, with no ng-controllers or ng-includes which is all apart of the process for component styled directives. next we are gonna bind variable to the controller that you specify on the html like this [GIST add Binding](https://gist.github.com/GreenPioneer/e4b6b1f5938f40c5798b)

Next Step: Add a two new attributes to the html one for the username and one for the list of fiddles.

## Example 1 - Pull it all together

Next Step:Take this [GIST](https://gist.github.com/GreenPioneer/3d835d2418886f464c7f) and start pulling out what you need. fist you will need to pass the username to the directive. You will also need to send the data you got to the directive as a list. You will also need to wire up your ng repeat to display the proper data . 

## Example 2 - Take it a step further

The answer lives in the git hub repo for those whos want to see the code and for those of you who want to try to go a spet further then follow the directions bellow.

Next Step: Create 1 provide , 1 Factory & 1 Config: 1st that creates and the username , 2nd create a factory that is your resource to query the api. 3rd create a config that sets the provider to save your username which can be set at anytime in the program really. In doing all of this you will need to remove you main control because these three providers will handle all of your logic and you can inject them straight into the directive as need be.



#### This is [on GitHub](https://github.com/GreenPioneer/angular_Factories_Services_Providers)
#### Find us [on GitHub](https://github.com/GreenPioneer)
#### Find us [on Twitter](https://twitter.com/greenpioneerdev)
#### Find us [on Facebook](https://www.facebook.com/Green-Pioneer-Solutions-1023752974341910)
#### Find us [on The Web](http://greenpioneersolutions.com/)