# shoponline
Objects (with Behaviors and State): 
	Object : Consumer
		State : name, address
		Behavior : visitWebsite(), findBooks(), placeOrderForBook(), payMoneyToWebsite()
	
	
	Object : ShoppingWebsite
		State : Collection of Books
		Behavior : displayAvailableBooks(), shipABookToConsumer(), acceptMoneyFromConsumer()
	
	Object : Book
		State : name, price, author
		Behavior : getPrice(), getName()
	
	Object : Money
		state : amount	

class Consumer{
	String name;
	String address;
	void visitWebsite(ShoppingWebsite sw){}
	Book findTheBookInterestedIn(Book books[]){}
	void placeOrderForBook(Book book){}
	Money payMoneyToWebsite(ShoppingWebsite sw){}
	
}

class ShoppingWebsite{
	Book[] books; //Array of Book
	Book[] displayAvailableBooks(){}
	void shipABookToConsumer(Consumer c, Book b){}
	void acceptMoneyFromConsumer(Consumer c, Money money){}
			
}

class Book{
	String name, author;
	Float price;
	Float getPrice(){}
	String getName(){}

}

class Money{
	float amount;
}

class ShoppingOnline{
	public static void main(String args[]){
		ShoppingWebsite amazon = new ShoppingWebsite();

		Book headFirstJava = new Book();headFirstJava.name = "Head First Java";
		Book thinkingJava = new Book();thinkingJava = "Thinking In Java";
		Book[] books = {headFirstJava, thinkingJava};

		Consumer michael = new Consumer();
		michael.name = "Michael";
		
		michael.visitsWebsite(amazon);
		Book[] books = amazon.displayAvailableBooks();
		Book book = michael.findTheBookInterestedIn( books , amazon);
		michael.placeOrderForBook(book, amazon)
		Money money = michael.payMoneyToWebsite(amazon);
		amazon.acceptMoneyFromConsumer(michael, money);
	}

}
