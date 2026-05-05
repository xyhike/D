import java.util.*;

public class RingSimple {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of processes: ");
        int n = sc.nextInt();

        boolean[] alive = new boolean[n];

        // Initially all processes are alive
        for (int i = 0; i < n; i++) {
            alive[i] = true;
        }

        System.out.print("Enter failed process ID: ");
        int failed = sc.nextInt();
        alive[failed - 1] = false;

        System.out.print("Enter process to start election: ");
        int start = sc.nextInt();

        ArrayList<Integer> list = new ArrayList<>();

        int current = start;

        System.out.println("\nElection starts:\n");

        do {
            if (alive[current - 1]) {
                list.add(current);

                System.out.print("Process " + current + " sends: ");
                System.out.println(list);
            }

            // Move to next process in ring
            current = (current % n) + 1;

        } while (current != start);

        // Find leader (max ID)
        int leader = Collections.max(list);

        System.out.println("\nLeader elected: Process " + leader);

        sc.close();
    }
}
