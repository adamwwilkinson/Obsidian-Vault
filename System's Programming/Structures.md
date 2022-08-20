# Structures
Created: 16/08/2022 at 10:05
Tags: #topic/programming 
Related: [[The Programming Language C]]

### Defining
A method to gather and collect data.
```c
struct {
	char* name;
	int red;
	int blue;
	int green;
} rgb_colour = {
		"Dogerblue",
		30,
		144,
		255
};
```
```c
//  DEFINE THE LIMITS ON PROGRAM'S DATA-STRUCTURES
#define MAX_TEAMS               24
#define MAX_TEAMNAME_LEN        30

struct {
    char    teamname[MAX_TEAMNAME_LEN+1];        // +1 for null-byte

//  STATISTICS FOR THIS TEAM, INDEXED BY EACH TEAM'S 'TEAM NUMBER'
    int     played;
    int     won;
    int     lost;
    int     drawn;
    int     bfor;
    int     bagainst;
    int     points;
} team[MAX_TEAMS];    //  DEFINE A 1-DIMENSIONAL ARRAY NAMED team
```

### Accessing Fields
```c
//  PRINT EACH TEAM'S RESULTS, ONE-PER-LINE, IN NO SPECIFIC ORDER
for(int t=0 ; t<nteams ; ++t) {
    printf("%s %i %i %i %i %i %i %.2f %i\n", // %age to 2 decimal-places
            team[t].teamname,
            team[t].played, team[t].won, team[t].lost, team[t].drawn,
            team[t].bfor, team[t].bagainst,
            (100.0 * team[t].bfor / team[t].bagainst),      // calculate percentage
            team[t].points);
}
```