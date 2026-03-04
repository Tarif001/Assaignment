# Assaignment
abstract class FootballPlayer {
    protected String name;
    protected int goals;
    private double monthlySalary;  

    public FootballPlayer(String name, int goals, double monthlySalary) {
        this.name = name;
        this.goals = goals;
        this.monthlySalary = monthlySalary;
    }
 
    public abstract double calculateGoalRate(int matchesPlayed);
 
    public void displayInfo(String league, double goalRate) {
        System.out.println("--- Player Details ---");
        System.out.println("Name       : " + name);
        System.out.println("League     : " + league);
        System.out.println("Goals      : " + goals);
        System.out.println("Goal Rate  : " + String.format("%.2f", goalRate) + " per match");
        System.out.println();
    }
}

 
class LaLigaPlayer extends FootballPlayer {
    public LaLigaPlayer(String name, int goals, double monthlySalary) {
        super(name, goals, monthlySalary);
    }

    @Override
    public double calculateGoalRate(int matchesPlayed) {
        if (matchesPlayed == 0) return 0;
        return (double) goals / matchesPlayed;
    }
}

 
class PremierLeaguePlayer extends FootballPlayer {
    public PremierLeaguePlayer(String name, int goals, double monthlySalary) {
        super(name, goals, monthlySalary);
    }

    @Override
    public double calculateGoalRate(int matchesPlayed) {
        if (matchesPlayed == 0) return 0;
        return (double) goals / matchesPlayed;
    }
}

 
public class FootballSystem {
    public static void main(String[] args) {
        
        LaLigaPlayer messi = new LaLigaPlayer("Lionel Messi", 672, 5000000);
        double messiRate = messi.calculateGoalRate(778);
        messi.displayInfo("La Liga", messiRate);
 
        PremierLeaguePlayer ronaldo = new PremierLeaguePlayer("Cristiano Ronaldo", 145, 4000000);
        double ronaldoRate = ronaldo.calculateGoalRate(346);
        ronaldo.displayInfo("Premier League", ronaldoRate);
    }
}
