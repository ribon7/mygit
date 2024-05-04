#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>
int main() {
    char* f[3] = {"가위", "바위", "보"}; // 가위, 바위, 보를 배열에 순서대로 저장
    int num; 
  int n=3; //컴퓨터가 낼 것의 개수
    char in[10]; //사용자가 입력할 값을 저장할 변수
    srand(time(NULL)); //현재 시간을 기반으로 난수 발생기를 초기화
   printf("가위, 바위, 보 ,종료 중에서 선택하세요: ");
 while(1){
  scanf("%s", in);
   num = rand() % 3; //난수 생성 함수에 생성된 난수를 3을 나눴을 때 나머지값을 num에 저장
   if((strcmp(in, "종료") == 0)){ //입력한 문자열이 '종료'라면 0을 반환, 0과 같을 때 whlle문을 벗어나며 프로그램 종료
    printf("끝");
    break;
   }
  printf("당신의 선택: %s\n", in); //사용자가 입력한 값을 출력
  printf("컴퓨터의 선택: %s\n", f[num]); //난수를 이용하여 컴퓨터가 낼 것을 결정

      if ((strcmp(in, "가위") == 0 && num == 2) || //사용자가 가위를 입력했을 때 0으로 변환되고 컴퓨터가 생성한 값인 2, f[2]='보'인 상황이 동시에 발생했을 때 사용자가 이겼음을 출력
          (strcmp(in, "바위") == 0 && num == 0) ||
          (strcmp(in, "보") == 0 && num == 1)) {
        printf("당신이 이겼습니다!\n");
      }
      else if 
        ((strcmp(in, "가위") == 0 && num == 1) || //사용자가 지는 경우 
         (strcmp(in, "바위") == 0 && num == 2) ||
         (strcmp(in, "보") == 0 && num == 0))
      {
        printf("컴퓨터가 이겼습니다!\n");
      }
      else if
           ((strcmp(in, "가위") == 0 && num == 0) || //사용자가 비기는 경우
            (strcmp(in, "바위") == 0 && num == 1) ||
            (strcmp(in, "보") == 0 && num == 2))
      {
        printf("무승부입니다\n"); 
      }
      else{
        printf("잘못된 입력입니다. 다시 입력하세요.\n");//잘못된 입력을 받았을 때 다시 입력하라는 문구 출력
      }
   }
}
