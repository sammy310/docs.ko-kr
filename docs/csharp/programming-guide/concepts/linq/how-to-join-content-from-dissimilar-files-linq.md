---
title: 서로 다른 파일의 콘텐츠를 조인하는 방법(LINQ)(C#)
ms.date: 06/27/2018
ms.assetid: aa2d12a6-70a9-492f-a6db-b2b850d46811
ms.openlocfilehash: efe11c31873f21841c28bd393b295eea117d1e46
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169092"
---
# <a name="how-to-join-content-from-dissimilar-files-linq-c"></a><span data-ttu-id="b6970-102">서로 다른 파일의 콘텐츠를 조인하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="b6970-102">How to join content from dissimilar files (LINQ) (C#)</span></span>

<span data-ttu-id="b6970-103">이 예제에서는 일치하는 키로 사용되는 공통 값을 공유하는 두 개의 쉼표로 구분된 파일의 데이터를 조인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-103">This example shows how to join data from two comma-delimited files that share a common value that is used as a matching key.</span></span> <span data-ttu-id="b6970-104">이 방법은 두 스프레드시트나 한 스프레드시트와 다른 형식으로 된 파일의 데이터를 하나의 새 파일로 결합해야 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-104">This technique can be useful if you have to combine data from two spreadsheets, or from a spreadsheet and from a file that has another format, into a new file.</span></span> <span data-ttu-id="b6970-105">모든 종류의 구조적 텍스트에서 작동하도록 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-105">You can modify the example to work with any kind of structured text.</span></span>  
  
## <a name="to-create-the-data-files"></a><span data-ttu-id="b6970-106">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b6970-106">To create the data files</span></span>
  
1. <span data-ttu-id="b6970-107">다음 줄을 *scores.csv* 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-107">Copy the following lines into a file that is named *scores.csv* and save it to your project folder.</span></span> <span data-ttu-id="b6970-108">파일은 스프레드시트 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-108">The file represents spreadsheet data.</span></span> <span data-ttu-id="b6970-109">열 1은 학생 ID이고, 열 2-5는 시험 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-109">Column 1 is the student's ID, and columns 2 through 5 are test scores.</span></span>  
  
    ```csv  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
2. <span data-ttu-id="b6970-110">다음 줄을 *names.csv* 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-110">Copy the following lines into a file that is named *names.csv* and save it to your project folder.</span></span> <span data-ttu-id="b6970-111">파일은 학생의 성, 이름 및 학생 ID를 포함하는 스프레드시트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6970-111">The file represents a spreadsheet that contains the student's last name, first name, and student ID.</span></span>  
  
    ```csv  
    Omelchenko,Svetlana,111  
    O'Donnell,Claire,112  
    Mortensen,Sven,113  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Hugo,118  
    Tucker,Lance,119  
    Adams,Terry,120  
    Zabokritski,Eugene,121  
    Tucker,Michael,122  
    ```  
  
## <a name="example"></a><span data-ttu-id="b6970-112">예제</span><span class="sxs-lookup"><span data-stu-id="b6970-112">Example</span></span>  

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

class JoinStrings  
{  
    static void Main()  
    {  
        // Join content from dissimilar files that contain  
        // related information. File names.csv contains the student  
        // name plus an ID number. File scores.csv contains the ID
        // and a set of four test scores. The following query joins  
        // the scores to the student names by using ID as a  
        // matching key.  
  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Name:    Last[0],       First[1],  ID[2]  
        //          Omelchenko,    Svetlana,  11  
        // Score:   StudentID[0],  Exam1[1]   Exam2[2],  Exam3[3],  Exam4[4]  
        //          111,           97,        92,        81,        60  
  
        // This query joins two dissimilar spreadsheets based on common ID value.  
        // Multiple from clauses are used instead of a join clause  
        // in order to store results of id.Split.  
        IEnumerable<string> scoreQuery1 =  
            from name in names  
            let nameFields = name.Split(',')  
            from id in scores  
            let scoreFields = id.Split(',')  
            where Convert.ToInt32(nameFields[2]) == Convert.ToInt32(scoreFields[0])
            select nameFields[0] + "," + scoreFields[1] + "," + scoreFields[2]
                   + "," + scoreFields[3] + "," + scoreFields[4];  
  
        // Pass a query variable to a method and execute it  
        // in the method. The query itself is unchanged.  
        OutputQueryResults(scoreQuery1, "Merge two spreadsheets:");  
  
        // Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void OutputQueryResults(IEnumerable<string> query, string message)  
    {  
        Console.WriteLine(System.Environment.NewLine + message);  
        foreach (string item in query)  
        {  
            Console.WriteLine(item);  
        }  
        Console.WriteLine("{0} total names in list", query.Count());  
    }  
}  
/* Output:  
Merge two spreadsheets:
Omelchenko, 97, 92, 81, 60
O'Donnell, 75, 84, 91, 39
Mortensen, 88, 94, 65, 91
Garcia, 97, 89, 85, 82
Garcia, 35, 72, 91, 70
Fakhouri, 99, 86, 90, 94
Feng, 93, 92, 80, 87
Garcia, 92, 90, 83, 78
Tucker, 68, 79, 88, 92
Adams, 99, 82, 81, 79
Zabokritski, 96, 85, 91, 60
Tucker, 94, 92, 91, 91
12 total names in list
 */  
```

## <a name="see-also"></a><span data-ttu-id="b6970-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6970-113">See also</span></span>

- [<span data-ttu-id="b6970-114">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="b6970-114">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="b6970-115">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="b6970-115">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
