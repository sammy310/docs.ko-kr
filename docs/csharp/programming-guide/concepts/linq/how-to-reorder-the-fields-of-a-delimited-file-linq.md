---
title: 구분된 파일의 필드를 다시 정렬하는 방법(LINQ)(C#)
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 6bc502ff12a908edf43f9ff7f5f63f98c3ff29c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347648"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="96817-102">구분된 파일의 필드를 다시 정렬하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="96817-102">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>
<span data-ttu-id="96817-103">쉼표로 구분된 값(CSV) 파일은 스프레드시트 데이터 또는 행과 열로 표현되는 다른 테이블 형식 데이터를 저장하는 데 자주 사용되는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="96817-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="96817-104"><xref:System.String.Split%2A> 메서드를 사용하여 필드를 구분하면 LINQ를 사용하여 쉽게 CSV 파일을 쿼리하고 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96817-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="96817-105">실제로 동일한 방법을 사용하여 모든 구조적 텍스트 줄의 일부를 다시 정렬할 수 있습니다. CSV 파일로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96817-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="96817-106">다음 예제에서는 세 개의 열이 학생의 "last name", "first name" 및 "ID"를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="96817-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="96817-107">필드는 학생의 성을 기준으로 알파벳 순서로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="96817-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="96817-108">쿼리는 ID 열이 첫 번째로 표시되고, 학생의 이름과 성을 결합하는 두 번째 열이 뒤에 오는 새 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="96817-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="96817-109">ID 필드에 따라 줄이 다시 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="96817-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="96817-110">결과는 새 파일에 저장되고 원래 데이터가 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96817-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="96817-111">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="96817-111">To create the data file</span></span>  
  
1. <span data-ttu-id="96817-112">spreadsheet1.csv라는 일반 텍스트 파일에 다음 줄을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="96817-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="96817-113">프로젝트 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96817-113">Save the file in your project folder.</span></span>  
  
    ```csv  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="96817-114">예제</span><span class="sxs-lookup"><span data-stu-id="96817-114">Example</span></span>  
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96817-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="96817-115">Compiling the Code</span></span>  
<span data-ttu-id="96817-116">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96817-116">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="96817-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96817-117">See also</span></span>

- [<span data-ttu-id="96817-118">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="96817-118">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="96817-119">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="96817-119">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
- [<span data-ttu-id="96817-120">CSV 파일에서 XML을 생성하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="96817-120">How to generate XML from CSV files (C#)</span></span>](./how-to-generate-xml-from-csv-files.md)
