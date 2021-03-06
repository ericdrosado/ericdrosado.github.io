<h2> Intro: </h2>
SRP! The big fish of the SOLID world. It seems to me that out of all of the SOLID principles (Single Responsibility Principle, Open/Closed Principle, Liskov Substitution Principle, Interface Segregation , Dependency Inversion) the Single Responsibility Principle (SRP) plays a role/ties all of the principles together. The Single Responsibility Principle states that each class and each method should have a single responsibility. As Uncle Bob would say, "A class should have only one reason to change," which ultimately means that a class should have responsibility over a single part of functionality in a piece of software. In this post I would like to take an opportunity to explore some details of SRP and why is it important in the grand scheme of Object Oriented Programming (OOP).

<h2> SRP Example </h2>
I would like to use an example as a means to guide our exploration into SRP. Think of developing software for an art gallery. In the gallery they have a large array of art work that needs some cataloging which gives an art gallery employee the name of the artwork, the artists name, a description of the work, the location of the item in the gallery, and a means of printing the information out. Lets say we put all of these things in a single class to start named Artwork:

    class Artwork

      def get_title title
        puts title
      end

      def get_artist artist
        puts artist
      end

      def get_description description
        puts description
      end

      def get_location location
        puts location
      end

    end

After observing this class one might think...not bad, all the information that the curators at the gallery needed are in this class and everything is pretty accessible by calling one of the methods and passing a parameter. Well, not so my friend. There are a few instances where we are violating SRP.

The first violation may be obvious, which is the fact that we are printing in every single method. Printing in itself has nothing to do with the logic of the artwork. We should be doing one thing and one thing only in each method. If a curator wants a title then he should be able to get the information they need from a call and print it elsewhere. So, how about this:

    class Artwork

      def get_title title
        title
      end

      def get_artist artist
        artist
      end

      def get_description description
        description
      end

      def get_location location
        location
      end

      def print information_to_print
        puts information_to_print
      end

    end

Well, at this point we have pulled the logic of printing out of the methods and placed it into its own method in the Artwork class. This should also raise a red flag. We have now created a method in the class Artwork that has nothing to do with the Artwork as a whole. Artwork is suppose to provide information about the Artwork to the curator and the printing logic should not be considered a part of this class. So perhaps this will be better:

    class Artwork

      def get_title title
        title
      end

      def get_artist artist
        artist
      end

      def get_description description
        description
      end

      def get_location location
        location
      end

    end

    class Printer

      def print information_to_print
        puts information_to_print
      end

    end

Now this is much better as we can make calls to printer if the curator needs to print certain information. Our code is now cleaner and offers us great flexibility if something is to be changed later on. 

Well, we are not quite done yet. Can you see something else that we might want to change? Remember, the Artwork class is made to provide information to the curator about the artwork in itself. Is there a method that we can pull from the Artwork class? Yes! That location class could probably move as it provides information about the location of the artwork, but not specific information that would be considered an attribute of artwork. Confused? Think about it this way, the artwork in itself is not dependent on location in order to identify it. The title, the artist name, and the description are attributes of the class and the location could change at any point so it is independent. So perhaps something like this would be better:

    class Artwork

      def get_title title
        title
      end

      def get_artist artist
        artist
      end

      def get_description description
        description
      end

    end

    class Printer

      def print information_to_print
        puts information_to_print
      end

    end

    class Location

      def get_location location
        location
      end

    end

Our software now offers great flexbility if something should change and now we have created reuseable classes that our software could utilize as it grows over time.

<h2> Conclusion </h2>
SRP is obviously important when it comes to flexibility of our software. If we think back to our Artwork example, perhaps in the future the curators want to make specific classes of artwork such as paintings, sculptures, and so forth. We are prepared to extend our software because we have made it flexible. We are also able to reuse our printing and location classes for these new classes that are to be added. With SRP we have set ourselves up to develop clean Object Oriented (OO) code.


