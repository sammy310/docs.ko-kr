---
title: 그룹을 사용하여 파일을 여러 파일로 분할하는 방법(LINQ)(C#)
description: 그룹을 사용하여 파일을 여러 파일로 분할하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
ms.assetid: 8179b91c-d778-4e57-884f-77fe5a8e4e40
ms.openlocfilehash: 1db16a48db257069eca83127c0b1fed7e49f19d6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301062"
---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-c"></a><span data-ttu-id="92c56-104">그룹을 사용하여 파일을 여러 파일로 분할하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="92c56-104">How to split a file into many files by using groups (LINQ) (C#)</span></span>
<span data-ttu-id="92c56-105">이 예제에서는 두 파일의 내용을 병합한 다음 새로운 방식으로 데이터를 구성하는 새 파일 집합을 만드는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92c56-105">This example shows one way to merge the contents of two files and then create a set of new files that organize the data in a new way.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="92c56-106">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="92c56-106">To create the data files</span></span>  
  
1. <span data-ttu-id="92c56-107">이러한 이름을 names1.txt 텍스트 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="92c56-107">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```text  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2. <span data-ttu-id="92c56-108">이러한 이름을 names2.txt 텍스트 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다. 두 파일에서 일부 이름은 공통됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c56-108">Copy these names into a text file that is named names2.txt and save it in your project folder: Note that the two files have some names in common.</span></span>  
  
    ```text  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="92c56-109">예제</span><span class="sxs-lookup"><span data-stu-id="92c56-109">Example</span></span>  
  
```csharp  
class SplitWithGroups  
{  
    static void Main()  
    {  
        string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Concatenate and remove duplicate names based on  
        // default string comparer  
        var mergeQuery = fileA.Union(fileB);  
  
        // Group the names by the first letter in the last name.  
        var groupQuery = from name in mergeQuery  
                         let n = name.Split(',')  
                         group name by n[0][0] into g  
                         orderby g.Key  
                         select g;  
  
        // Create a new file for each group that was created  
        // Note that nested foreach loops are required to access  
        // individual items with each group.  
        foreach (var g in groupQuery)  
        {  
            // Create the new file name.  
            string fileName = @"../../../testFile_" + g.Key + ".txt";  
  
            // Output to display.  
            Console.WriteLine(g.Key);  
  
            // Write file.  
            using (System.IO.StreamWriter sw = new System.IO.StreamWriter(fileName))  
            {  
                foreach (var item in g)  
                {  
                    sw.WriteLine(item);  
                    // Output to console for example purposes.  
                    Console.WriteLine("   {0}", item);  
                }  
            }  
        }  
        // Keep console window open in debug mode.  
        Console.WriteLine("Files have been written. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:
    A  
       Aw, Kam Foo  
    B  
       Bankov, Peter  
       Beebe, Ann  
    E  
       El Yassir, Mehdi  
    G  
       Garcia, Hugo  
       Guy, Wey Yuan  
       Garcia, Debra  
       Gilchrist, Beth  
       Giakoumakis, Leo  
    H  
       Holm, Michael  
    L  
       Liu, Jinghao  
    M  
       Myrcha, Jacek  
       McLin, Nkenge  
    N  
       Noriega, Fabricio  
    P  
       Potra, Cristina  
    T  
       Toyoshima, Tim  
 */  
```  
  
 <span data-ttu-id="92c56-110">프로그램에서 데이터 파일과 동일한 폴더에 각 그룹에 대한 별도 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="92c56-110">The program writes a separate file for each group in the same folder as the data files.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92c56-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="92c56-111">Compiling the Code</span></span>

<span data-ttu-id="92c56-112">System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 통해 C# 콘솔 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="92c56-112">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92c56-113">참조</span><span class="sxs-lookup"><span data-stu-id="92c56-113">See also</span></span>

- [<span data-ttu-id="92c56-114">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="92c56-114">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="92c56-115">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="92c56-115">LINQ and File Directories (C#)</span></span>](./linq-and-file-directories.md)
