#include <iostream>
#define MAX 100
using namespace std;

int arr[MAX][MAX], crr[MAX]; //arr배열은 물풍선 터지기 전, 후 나타낼 배열, crr배열은 플레이어 생존여부 결정 배열

int main()
{
	int i, j, k;

	for(i=1; i<=10; i++) //10x10에 입력 과정
		for (j = 1; j <= 10; j++)
		{
			cin >> arr[i][j];
		
		}

	for(i=1; i<=10; i++) //10x10에서 물풍선(0보다큰수)를 찾아서 터트리기 위한 과정
		for (j = 1; j <= 10; j++)
		{
			if (arr[i][j] > 0) //0보다 큰 물풍선이라면
			{
				int up = 0, down = 0, right = 0, left = 0; //위, 아래, 오른, 왼쪽으로 더 갈지 혹은 멈출지 정할 변수
				for (k = 1; k <= arr[i][j]; k++) //1부터 물풍선 크기까지
				{
					arr[i][j] = -2; //물풍선이 있는 자리는 우선 -2
					
					
					if (arr[i - k][j] != -1 && up == 0 && arr[i-k][j] <=0) //위에가 -1(장애물)이 아니면서 up에 제약이 안 걸리면서 0보다 값이 작은경우
						arr[i - k][j] = -2; //물풍선 범위로 간주
					else if (arr[i-k][j] == -1 || (i-k <0)) // 위가 장애물이거나 배열 범위를 벗어난경우
						up = 1; //up에 제약을 검

					//아래, 오른, 왼쪽 코드도 동일한 형태
					if (arr[i + k][j] != -1 && down == 0 && arr[i + k][j] <= 0)
						arr[i + k][j] = -2;
					else if (arr[i + k][j] == -1 || (i + k > 99))
						down = 1;

					if (arr[i][j+k] != -1 && right == 0 && arr[i][j+k] <= 0)
						arr[i][j+k] = -2;
					else if (arr[i][j+k] == -1 || (j + k >99))
						right = 1;

					if (arr[i][j-k] != -1 && left == 0 && arr[i][j-k] <= 0)
						arr[i][j-k] = -2;
					else if (arr[i][j-k] == -1 || (j-k < 0))
						left = 1;
				}
			}
		}

	int playernum, a, b;

	cin >> playernum; //플레이어 수 입력

	for (i = 1; i <= playernum; i++) //플레이어수 만큼 반복
	{
		cin >> a >> b; //행 열 좌표 입력

		if (arr[a][b] == 0) //그 좌표가 0이라면(물풍선이 안닿음)
		{
			arr[a][b] = i; //i번째 이므로 i를 넣어줌
			crr[i]++; //생존 확인 배열에 1값이 들어감(배열 자체가 0으로 초기화된 상태)
		}
		else
			;
	}

	for (i = 1; i <= 10; i++) //물풍선 터진후 상태 출력
	{
		for (j = 1; j <= 10; j++)
		{
			cout << arr[i][j] << " ";
		}
		cout << "\n";
	}

	cout << "Character Information" <<endl;
	for (i = 1; i <= playernum; i++) //캐릭터 생존 여부 출력(crr배열값이 1이라면 생존)
	{
		if (crr[i] == 1)
			cout << "player " << i << " " << "survive" << endl;
		else
			cout << "player " << i << " " << "dead"<<endl;
	}

}
