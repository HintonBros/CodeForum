## Chat program example prototype


```Java
interface IInterface {
  public void setActionListener(ActionListener listener);
  public void refresh(String[] messages);
}

interface IStore {
  public void save(String message);
  public String[] retrieve(Int last);
}

class CLIInterface implements IInterface {
  public void refresh(String[] messages) {
    // implementation  
  }
  
  public void setActionListener(ActionListener listener) {
    // implementation
  }
}

class SQLStore implements IStore {
  public void save(String message) {
    // implementation
  }
  public String[] retrieve(Int last) {
    // implementation
  }
  
}


class Chat {
  public IStore store;
  public Chat(IStore store) {
      store = store;
  }
  
  public String[] getLatestMessages(Int count) {
    return store.retrieve(count);
  }
}

class ChatInterfaceController implements ActionListener { 
  public IInterface interface;
  public Chat chat;
  public ChatInterfaceController(interface: IInterface, chat: Chat) {
    interface = interface;
    chat = chat;
    interface.refresh(chat.getMessages(5));
  }
  
  public void actionPerformed(ActionEvent e) {
    
  }
}

class Main {
  public static void main(String args[]){
    Chat chat = new Chat(new SQLStore());
    ChatInterfaceController controller = ChatInterfaceController(new CLIInterface(), chat);
  }
}


```
