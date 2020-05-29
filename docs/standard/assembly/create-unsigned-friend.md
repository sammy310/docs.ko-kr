---
title: '방법: 서명되지 않은 friend 어셈블리 만들기'
description: 이 문서에서는 서명되지 않은 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다. .NET 보안에 대한 정보를 포함합니다.
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: 8d3e13669c36048759fedeb3df1bfb59fd476317
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378964"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="c1592-104">방법: 서명되지 않은 friend 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="c1592-104">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="c1592-105">이 예제에서는 서명되지 않은 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-105">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="c1592-106">어셈블리 및 friend 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="c1592-106">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="c1592-107">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-107">Open a command prompt.</span></span>

2. <span data-ttu-id="c1592-108">다음 코드를 포함하는 *friend_unsigned_A*라는 C# 또는 Visual Basic 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-108">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="c1592-109">이 코드는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 사용하여 *friend_unsigned_B*를 friend 어셈블리로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-109">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
   Imports System.Runtime.CompilerServices

   <Assembly: InternalsVisibleTo("friend_unsigned_B")>

   ' Friend type.
   Friend Class Class1
       Public Sub Test()
           Console.WriteLine("Class1.Test")
       End Sub
   End Class

   ' Public type with Friend member.
   Public Class Class2
       Friend Sub Test()
           Console.WriteLine("Class2.Test")
       End Sub
   End Class
   ```

3. <span data-ttu-id="c1592-110">다음 명령을 사용하여 *friend_unsigned_A*를 컴파일하고 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-110">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="c1592-111">다음 코드를 포함하는 *friend_unsigned_B*라는 C# 또는 Visual Basic 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-111">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="c1592-112">*friend_unsigned_A*는 *friend_unsigned_B*를 friend 어셈블리로 지정하기 때문에 *friend_unsigned_B*는 *friend_unsigned_A*의 `internal`(C#) 또는 `Friend`(Visual Basic) 형식과 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-112">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

   ```vb
   ' friend_unsigned_B.vb
   ' Compile with:
   ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   Module Module1
       Sub Main()
           ' Access a Friend type.
           Dim inst1 As New Class1()
           inst1.Test()

           Dim inst2 As New Class2()
           ' Access a Friend member of a public type.
           inst2.Test()

           System.Console.ReadLine()
       End Sub
   End Module
   ```

5. <span data-ttu-id="c1592-113">다음 명령을 사용하여 *friend_unsigned_B*를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-113">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="c1592-114">컴파일러에서 생성된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성에 전달된 friend 어셈블리 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-114">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="c1592-115">`-out` 컴파일러 옵션을 사용하여 출력 어셈블리( *.exe* 또는 *.dll*)의 이름을 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-115">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="c1592-116">자세한 내용은 [-out(C# 컴파일러 옵션)](../../csharp/language-reference/compiler-options/out-compiler-option.md) 또는 [-out(Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1592-116">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="c1592-117">*friend_unsigned_B.exe* 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-117">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="c1592-118">프로그램에서 두 개의 문자열 **Class1.Test** 및 **Class2.Test**가 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-118">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="c1592-119">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="c1592-119">.NET security</span></span>

<span data-ttu-id="c1592-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성과 <xref:System.Security.Permissions.StrongNameIdentityPermission> 클래스 간에는 유사점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-120">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="c1592-121">주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 코드의 특정 섹션을 실행하는 보안 권한을 요구할 수 있는 반면, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 `internal` 또는 `Friend`(Visual Basic) 형식 및 멤버의 표시 유형을 제어한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1592-121">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1592-122">참조</span><span class="sxs-lookup"><span data-stu-id="c1592-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="c1592-123">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c1592-123">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="c1592-124">friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="c1592-124">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="c1592-125">방법: 서명된 friend 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="c1592-125">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="c1592-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c1592-126">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c1592-127">프로그래밍 개념(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1592-127">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
