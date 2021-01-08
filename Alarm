import java.util.Timer;
import java.util.TimerTask;
import java.util.Date;

public class Alarm{

    private final String name; //name of the timer
    private long time; //how much to is left to start playing
    private Timer timer; //obj
    private Date date;
    private final long currentDate;

    public Alarm(String name, long time){
        this.name = name;
        this.time = time;
        timer = new Timer();
        date = new Date();
        currentDate = date.getTime();
    }

    public void start(){
        timer.schedule(new AlarmTask(), currentDate - date.getTime() + time*1000);
    }

    public void delay(long delay){
        timer.cancel();
        time += delay;
        timer = new Timer();
        timer.schedule(new AlarmTask(), currentDate - date.getTime() + time*1000);
    }


    class AlarmTask extends TimerTask{
        @Override
        public void run() {
            System.out.println("Timer" + name + " is Ringing!!!");
            timer.cancel();
        }
    }
}
