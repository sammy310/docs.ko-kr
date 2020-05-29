---
title: '방법: 파일이 어셈블리인지 확인'
description: 이 문서에서는 파일이 .NET 어셈블리인지 여부를 수동으로 또는 프로그래밍 방식으로 확인하는 방법을 모두 보여 줍니다.
ms.date: 08/19/2019
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
dev_langs:
- csharp
- vb
ms.openlocfilehash: fb1bcfa50ec380f10ab67cc47331f91dc3e4b32d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380141"
---
# <a name="how-to-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="5f155-103">방법: 파일이 어셈블리인지 확인</span><span class="sxs-lookup"><span data-stu-id="5f155-103">How to: Determine if a file is an assembly</span></span>

<span data-ttu-id="5f155-104">파일은 관리되고 해당 메타데이터에 어셈블리 항목을 포함하는 경우에만 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-104">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="5f155-105">어셈블리 및 메타데이터에 대한 자세한 내용은 [어셈블리 매니페스트](manifest.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f155-105">For more information on assemblies and metadata, see [Assembly manifest](manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="5f155-106">파일이 어셈블리인지 수동으로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="5f155-106">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="5f155-107">[Ildasm.exe(IL 디스어셈블러)](../../framework/tools/ildasm-exe-il-disassembler.md)를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-107">Start the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="5f155-108">테스트하려는 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-108">Load the file you want to test.</span></span>  
  
3. <span data-ttu-id="5f155-109">**ILDASM**에서 파일이 PE(이식 가능) 파일이 아니라고 보고하는 경우에는 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-109">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="5f155-110">자세한 내용은 항목 [방법: 어셈블리 콘텐츠 보기](view-contents.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f155-110">For more information, see the topic [How to: View assembly contents](view-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="5f155-111">파일이 어셈블리인지 프로그래밍 방식으로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="5f155-111">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="5f155-112">테스트하는 파일의 전체 파일 경로와 이름을 전달하여 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-112">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="5f155-113"><xref:System.BadImageFormatException> 예외가 throw되는 경우 파일이 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-113">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f155-114">예제</span><span class="sxs-lookup"><span data-stu-id="5f155-114">Example</span></span>  
<span data-ttu-id="5f155-115">이 예제에서는 DLL을 테스트하여 어셈블리인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-115">This example tests a DLL to see if it is an assembly.</span></span>  

```csharp
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  

```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```

<span data-ttu-id="5f155-116"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드는 테스트 파일을 로드한 다음 정보를 읽고 나면 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5f155-116">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f155-117">참조</span><span class="sxs-lookup"><span data-stu-id="5f155-117">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="5f155-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5f155-118">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5f155-119">프로그래밍 개념(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f155-119">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="5f155-120">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="5f155-120">Assemblies in .NET</span></span>](index.md)
