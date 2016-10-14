TMP shi vinaxavt !   ! tu martivi ricxvia masivshi wers ! K - aris alagebs martiv ricxvebs miyolebit chawera ! tmp shevavset martivi ricxvebit !
shemdeg satitaod elementebis jams vamowmebt , tu jami martivi ricxvia vwyvitavt cillis shesrulebas - return 1 sakmarisia funqciidan gamosasvlelad  ! 2 ertmanetshi chasmuli cikli , 1 cikli aris imisatvis rom satitaod elemntebi avigot da shevadarot 
momdevnos !  sran NULL - aris mtlianad rand anu ricxvebi iwyeba saertod shemtxvevit ! 

! 

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>
#include <stdlib.h> 
#include <conio.h>
#include <time.h>

int isprime(int number) {
	int k = 2;
	int i = 1;
	while (k <= number / 2 ) {
		if (number % k == 0) {
			i = 0;
			break;
		}
		k++;
	}

	return i;
}

int is_sum_of_prime_numbers(int number) {	
	int tmp[100];
	int i = 0;
	int k = 0;

	/*for (i = 0; i < number; i++) {
		tmp[i] = 0;
	}*/

	i = 1;

	while (i < number) {
		if (isprime(i) == 1) {
			tmp[k] = i;
			k++;
		}
		i++;
	}

	for (int j = 0; j < k; j++) {
		for (i = j + 1; i < k; i++) {
			if (tmp[j] + tmp[i] == number) {
				printf("\n%02d + %02d = %02d \n\n", tmp[j], tmp[i], number);
				return 1;
			}
		}
	}

	return 0;
}

main()
{
	srand(time(NULL));
	int m[100];
	
	int i = 0;
	while (i < 100) {
		int r = rand() % 100;		
		printf("%02d ", r);
		
		if (r % 2 == 0 && is_sum_of_prime_numbers(r) == 1) {
			m[i] = r;
			i++;
		}
	}

	printf("\n\n");

	for (int i = 0; i < 100; i++) {
		//printf("%02d ", m[i]);		
	}

	printf("\n");
	getchar();	
}
