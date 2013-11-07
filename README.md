MapArray
========

Lab Week 10 Friday
import java.util.Random;
/**Lab Week 10 Friday
* @author Leon Liu
* @version 1.0 November 1 2013
*/
public class MapArray
{
public static void main (String[] args)
{
Random rand = new Random();

int size = 10;
int row = size;
int column = size;

char[][] map = new char[size + 2][size + 2];

for (int i = 0; i < map.length; i++)
{
for (int j = 0; j < map[0].length; j++)
{
map[i][j] = ' ';
}
}

while (row < map.length && column < map[0].length)
{

if (column == 0 || column == map.length - 1)
{
map[row][column] = '|';
}

if (row == 0 || row == map.length - 1)
{
map[row][column] = '-';
}
}

int sx = rand.nextInt(10);
int sy = rand.nextInt(10);

while (map[sy][sx] == '-' || map[sy][sx] == '|')
{
sx = rand.nextInt(10);
sy = rand.nextInt(10);
}

map[sy][sx] = 's';

int ex = rand.nextInt(10);
int ey = rand.nextInt(10);

while ((ex == sx && ey == sy) || (map[ey][ex] == '-' || map[ey][ex] == '|'))
{
ex = rand.nextInt(10);
ey = rand.nextInt(10);
}

map[ey][ex] = 'e';

row = 0;
column = 0;

int xd = ex - sx;
int yd = ey - sy;

while (row < map.length && column < map[0].length)
{
System.out.print(map[row][column]);
column++;

if (column == map[0].length)
{
System.out.println();
column = 0;
row++;
}
}

}
}
