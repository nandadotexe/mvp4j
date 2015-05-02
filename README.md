# mvp4j
MVP4J is a useful framework that is based primarily on practical design pattern MVP (Model View Presenter), therefore it facilitates the development of presentation layer technologies based on the principle of development events, it supports the different libraries Swing, AWT and GWT ( comming very soon ).

## Introduction :
Mvp4j provides a set of software components flexible and scalable, it's able to produce an application easy to maintain, these components are organized to be used in interaction with each other, in some advanced use cases, mvp4j allows the developer to implement its own component. Mvp4j requires an architecture based on the MVP design pattern to separate the layers described in classes and defining the responsibilities of each

## Architecture :

## The View :
The view is the main element of the framework, it consists of a set of core graphics component used in a single class or in some cases a set of classes with one that manages vision, called the class of the view (View class),access to the graphic components of the class of sight must pass through getter methods like getters of java beans.

### Example :
		@MVP(modelClass = ClientModel.class, presenterClass = ClientPresenter.class)
		public class ClientView extends JFrame {

		@Action(name = "actionExemple")
		JButton button;

		@Model(property = "modelProperty")
		JTextField textField;
		public ClientView() {

						setTitle("Client Application");
						setDefaultCloseOperation(EXIT_ON_CLOSE);
						setContentPane(new JPanel());
						setSize(1000, 600);
						setLocationRelativeTo(null);
						setLayout(null);
						add(getTextField());
						add(getButton());
				}



		  public JButton getButton() {
						if (button == null) {
								button = new JButton("OK");
								button.setBounds(10, 10, 70, 40);

						}
						return button;
				}


		public JTextField getTextField() {
				if (textField == null) {
								textField = new JTextField();
								textField.setBounds(70, 150, 150, 30);

				}
				return textField;
		   }


		}
		
## The Model :
Each view is associated with a single model, which is specified in a class that should have accessors (getter and setter) like the java beans, accessors access the data model used by the view.

### Example :
		public class ClientModel implements Serializable {

				private String modelProperty;
			  
			  public String getModelProperty() {
						return modelProperty;
				}

				public void setModelProperty(String modelProperty) {
						this.modelProperty = modelProperty;
				}
		}
		
## The Presenter :

The presenter manages the view, combining the events of the Views to the Presenter methods , these action methods must be defined in a java class called the Presenter class.

### Example :


