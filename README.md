# Pico-W-Nas-Expense-Tracker
Basically a Network expense tracker using a pi pico W and a decade old NAS pc.
Pico W → NAS Expense Tracker
Pico W sends expense data to a NAS server over WiFi.
Setup

Pico W
    
Download pico_w_server.py
Change WiFi: YOUR_WIFI_NAME and YOUR_WIFI_PASSWORD
Open Thonny, paste code, run 
make sure you saved it into the pi pico.

ssh (your nas username)@YOUR_NAS_IP
nano nas_receiver.py
paste code, save (Ctrl+X, Y, Enter)
python3 nas_receiver.py

Test it by running :
curl -X POST http://your_pico_ip:8000/ -d "amount=50&category=food"

ssh (your nas username)@YOUR_NAS_IP
cat /mnt/storage/expenses.txt

Updates#1
First upgrade for this project, i was able to add a prediction system that would predict how much your spending would be for next month. As long as you logging in your purchases daily into the pi pico w. 

To add this feature, run :
nano analyze_expenses.py in any terminals.
then copy paste expense_prediction1 into it then save and exit.

Updates #2 the previous prediction has been updateed so it tracks across months.
To implement this update, run nano analyze_expenses.py
then copy paste file expense_prediction2 into it then save and exit.
If you had implement updates #1 and are wondering how to update it, just run :
rm analyze_expenses.py (which deletes the previous one)
then just run nano analyze_expense.py and paste expense_prediction2

This would be my final update for this project most likely. Any confusions you may message me. 
Please give feedback about my project and any improvements i could possibly make. 
