---
layout: project
type: project
image: img/bank.jpg
title: "Banking Database"
date: 2024
published: true
labels:
  - C
  - C++
summary: "This is a banking database that I made for my ICS 212 class"
---

These projects were the two big projects that I had to complete in my Program Structures class. These projects spanned over a large majority of the semester. Completing this project included completing many different small assignments throughout the semester, leading up to the culmination of all of the information for the final result. The first project was the programming of this banking database in the language C. The second project was converting the same exact banking database into C++. 

For this project, I coded everything. Of course, with the guidance and instruction from my instructor, Ravi Narayan. The database provides a very simple and primitive user interface for the user. It gives the user five menu options to choose from, add (which adds a new record into the database), printall (which prints all of the records that are currently in the database), find (which returns the contents of a bank record once you provide the account number), delete (which deletes a record from the database once you provide the account number), and finally quit (which quits the application). The program also saves the records which allows you to access the same database every time you run the program.

From this project, I learned and became proficient in the coding language C. Learning C allowed me to gain a lot of knowledge about pointers, which are very important to know as a programmer. I also learned and became semi-proficient in C++. I learned the differences between C and C++ and found that coding in the different languages requires a different mindset from the other. 

Below is an excerpt of my deleteRecord function

```cpp
int deleteRecord(struct record ** start, int uaccountno)
{
    struct record * temp;
    struct record * temp2;
    int success = -1;

    if(debugmode == 1)
    {
        printf("\nDEBUG: Function name is deleteRecord\n");
        printf("DEBUG: Parameter uaccountno = %d\n\n", uaccountno);
    }

    if(*start == NULL)
    {
        success = -1;
    }
    else if(uaccountno == (*(*start)).accountno)
    {
        temp = *start;
        *start = (*(*start)).next;
        free(temp);
        success = 0;
    }
    else
    {
        temp = (*start);
        temp2 = (*temp).next;
        while(temp2 != NULL)
        {
            if(uaccountno == (*temp2).accountno)
            {
                (*temp).next = (*temp2).next;
                free(temp2);
                success = 0;
                temp2 = NULL;
            }
            else
            {
                temp = temp2;
                temp2 = (*temp2).next;

            }
        }
    }
    return success;
}
```


