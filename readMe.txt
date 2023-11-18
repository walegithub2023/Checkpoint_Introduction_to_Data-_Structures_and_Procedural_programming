# NAME OF REPOSITORY: Checkpoint_Introduction_to_Data _Structures_and_Procedural_programming



# DESCRIPTION: A repository for Checkpoint_Introduction_to_Data _Structures_and_Procedural_programming @ gomycode. This repo holds 2 algorithms that solve 2 problems.


	/*

	PROBLEM 1:

		Given two sets of elements, find the sum of all distinct elements from the set. In other words, find the sum of all elements which are present in either of the given set.

		Example:

		Set 1 : [3, 1, 7, 9], Set 2: [2, 4, 1, 9, 3]

		Output: 13 (distinct elements 4, 7, 2 )

		Give a solution to this problem, using arrays.

	*/





	/*

	PROBLEM 2:	

		1. Write a procedure, called dot_product which calculates in the variable ps, the dot(scalar) product of v1 and v2 (v1 and v2 are vectors of IR).

		2. Write an algorithm which determines, for n pairs of given vectors, whether two vectors of given IR are orthogonal, by calling the procedure defined in the previous question. The dot product     		   of two orthogonal vectors is zero.

		3. Modify the previous algorithm if you use a dot_product function instead of a procedure.

	*/




# Below are solutions to the afforementioned problems.

	SOLUTION TO PROBLEM 1:

	/*
	ALGORITHM PART 1: Function to create an array from user input.
	ALGORITHM PART 2: Function to check distinct of each of the array1 and array2.
	ALGORITHM PART 3: Sum the array distinct elements of array1 and array2.
	*/



	
	// ALGORITHM PART 1:




		// userArray Function Declaration/Creation

			FUNCTION userArray(n): ARRAY_OF INTEGER[n]           
	

    		//declare local variables for function userArray

    			i : INTEGER :=0;
    			userArray : ARRAY_OF INTEGER[n];                               

    		//receive array elements from user using for loop and return userArray

    			FOR i FROM 0 TO n-1 STEP 1  DO
        		Read(userArray[i]);          
        		i = i + 1;
    		
			END_FOR
    			RETURN userArray;





	// ALGORITHM PART 2: Function to check distinct array elements.

		//Declaration/creation of check_sum_distinct array.

		FUNCTION check_sum_distinct(y, z, array_1, array_2) : INTEGER         

    		// declare local variables for check_sum_distinct array.
    		y, z, sum, i, j := INTEGER;
    		array_1 : ARRAY_OF INTEGER [y];
    		array_2 : ARRAY_OF INTEGER [z];

    		// nested loop to compare each element in array 1 to array 2
    		FOR i FROM 0 TO y-1 STEP 1  DO                                         
        	FOR j FROM 0 TO z-1 STEP 1  DO
            
            	//if same item found in both arrays, break out of loop   
            	IF (array_1[i] == array_2[j]) THEN                           
                BREAK; 
            	END_IF
        	END_FOR
        
        	// if items not similar, add element to sum of distinct items from array 1
        	IF (array_1[i] <> array_2[j]) THEN                 
            	sum := sum + array_1[i];
        	END_IF
    		END_FOR

        	// Return sum of distinct
    		RETURN sum ;                                        
		END   





	// ALGORITHM PART 3: Sum the array distinct elements of array1 and array2.
		ALGORITHM sum_of_distinct

    		array1 : ARRAY_OF INTEGER[20];
    		array2 : ARRAY_OF INTEGER[20];
    		distinct, distinct1, distinct2, n, a, b = INTEGER :=0;


    		// prompt user to enter size of array between 1 and 20
    		// if number enter is not between and 20, then continue to prompt user again
    		REPEAT
       		write ("Enter size of first array between 1 and 20: ");
        	Read (a);
    		UNTIL (a > 0 AND a <= 20)

    		// call the function to get elements of the first array and set it to a variable
    		array1 := userArray(a);                                        

     		// prompt user to enter size of array between 1 and 20
    		// if number enter is not between and 20, then continue to prompt user again
    
    		REPEAT
        	write ("Enter size of second array:");
        	Read (b);
    		UNTIL (b > 0 AND b <= 20)
    
    		// call the function to get elements of the first array and set it to a variable
    		array2 := userArray(b);

    		// call the function to check for 
    		distinct1 := check_sum_distinct(a, b, array1, array2);
    		distinct2 := check_sum_distinct(b, a, array2, array1);
    		distinct := distinct1 + distinct2;

    		write(distinct);

END




	SOLUTION TO PROBLEM 2:

	/*
	ALGORITHM PART 1: Function to create an array from user input.
	ALGORITHM PART 2: Function to check distinct of each of the array1 and array2.
	ALGORITHM PART 3: Sum the array distinct elements of array1 and array2.
	*/


	// procedure declaration/creation
	PROCEDURE dot_product (VAR v1: ARRAY_OF INTEGER, VAR v2: ARRAY_OF INTEGER)

        
	// declare local variables

    	i, ps : INTEGER := 0;                                          

    	//check if length of vectors are equal then loop through array elements to multiply and get dot product

    	IF (v1.length == v2.length) THEN
        FOR i FROM 0 TO v1.length-1 STEP 1  DO
            ps = ps + v1[i] * v2[i];
        END_FOR
    	END_IF
	END



	/*
	Determine whether two vectors of given are orthogonal
	Orthogonal vectors are perpendicular vectors ie. dot product = 0
	1. Loop through each elements of each array.
	2. Find the dot product
	3. If dot product = 0 then the vectors (array) are orthogonal
	*/
	

	ALGORITHM orthogonal_procedure


	//declaration of global variables

    	vector_pairs : ARRAY_OF INTEGER[20][2];
    	i, j, n, ps : INTEGER


    	// to get number of vector pairs (between 1 and 20) from the user
    
        Write ("Enter number of vectors pairs between 1 and 20:");
        Read ("n");
    	UNTIL (a > 0 AND a <= 20)

    
    	//loop through array elements to allow user enter vector pairs
    	FOR i FROM 0 TO n-1 STEP 1  DO
        FOR j FROM 0 TO 1 STEP 1  DO
            // enter elements of vector pairs [i][j]
            Read (vector_pairs[i][j]);
        END_FOR
    	END_FOR


    	// loop through vector pairs to check for orthogonality
    	FOR i FROM 0 TO n-1 STEP 1  DO
        FOR j FROM 1 TO n-1 STEP step  DO
            IF (i <> j) THEN                                          // to ensure a vector pair is not multiplied by itself
                dot_product(vector_pairs[i], vector_pairs[j])      // call procedure to get dot product of 2 vector pairs
                IF (ps = 0) THEN                                    //
                    Write ("Vector Pairs ", i " and ", j " are orthogonal")     // if vectors are orthogonal, display notification
                END_IF
            END_IF
        END_FOR
    END_FOR
END






