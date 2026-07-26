public class BankAccount {

    private int balance;
    private boolean open;

    public synchronized void open() {
        balance = 0;
        open = true;
    }

    public synchronized void close() {
        if (!open) {
            throw new IllegalStateException("Account is closed");
        }
        open = false;
    }

    public synchronized int getBalance() {
        if (!open) {
            throw new IllegalStateException("Account is closed");
        }
        return balance;
    }

    public synchronized void deposit(int amount) {
        if (!open) {
            throw new IllegalStateException("Account is closed");
        }
        if (amount < 0) {
            throw new IllegalArgumentException("Cannot deposit negative amount");
        }
        balance += amount;
    }

    public synchronized void withdraw(int amount) {
        if (!open) {
            throw new IllegalStateException("Account is closed");
        }
        if (amount < 0) {
            throw new IllegalArgumentException("Cannot withdraw negative amount");
        }
        if (balance < amount) {
            throw new IllegalArgumentException("Insufficient funds");
        }
        balance -= amount;
    }
}
