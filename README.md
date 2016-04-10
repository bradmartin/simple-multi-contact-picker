# simple-multi-contact-picker
Simple Multi Contact Picker for Android 2.3+

The ContactsPickerActivity will show a list of contacts with phone number, from which a multiple contacts can be selected using the checkboxes provided alongside. 

The selected contacts will be returned as an ArrayList.

<h2>Usage:</h2>

Step 1:

Start the ContactsPickerActivity

<code>
Intent intentContactPick = new Intent(MainActivity.this,ContactsPickerActivity.class);
startActivityForResult(intentContactPick,1000);
</code>

Step 2:

After Selecting the contacts, receive the selected contacts

<code>
@Override

  public void onActivityResult(int requestCode,int resultCode,Intent data){
      super.onActivityResult(requestCode, resultCode, data);
  
      if(requestCode == CONTACT_PICK_REQUEST && resultCode == RESULT_OK){
  
          ArrayList<Contact> selectedContacts = data.getParcelableArrayListExtra("SelectedContacts");
          for(int i=0;i<selectedContacts.size();i++){
  
              String contact =  selectedContacts.get(i).toString();

          }

      }
  }

</code>

See MainActivity for sample usage.
