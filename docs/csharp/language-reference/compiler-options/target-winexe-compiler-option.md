---
description: -target:winexe(C# 컴파일러 옵션)
title: -target:winexe(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /target:winexe
helpviewer_keywords:
- /target compiler options [C#], /target:winexe
- -target compiler options [C#], /target:winexe
- target compiler options [C#], /target:winexe
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
ms.openlocfilehash: 5f8717115464ec3d9798228d7d50a8f08b2db300
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466094"
---
# <a name="-targetwinexe-c-compiler-options"></a><span data-ttu-id="f71f1-103">-target:winexe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f71f1-103">-target:winexe (C# Compiler Options)</span></span>
<span data-ttu-id="f71f1-104">**-target:winexe** 옵션을 사용하면 컴파일러가 Windows 프로그램 실행 파일(EXE)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-104">The **-target:winexe** option causes the compiler to create an executable (EXE), Windows program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71f1-105">구문</span><span class="sxs-lookup"><span data-stu-id="f71f1-105">Syntax</span></span>  
  
```console  
-target:winexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="f71f1-106">설명</span><span class="sxs-lookup"><span data-stu-id="f71f1-106">Remarks</span></span>  
 <span data-ttu-id="f71f1-107">실행 파일은 .exe 확장명으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-107">The executable file will be created with the .exe extension.</span></span> <span data-ttu-id="f71f1-108">Windows 프로그램은 .NET 라이브러리나 Windows API를 통해 사용자 인터페이스를 제공하는 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-108">A Windows program is one that provides a user interface from either the .NET library or with the Windows APIs.</span></span>  
  
 <span data-ttu-id="f71f1-109">[-target:exe](./target-exe-compiler-option.md)를 사용하여 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-109">Use [-target:exe](./target-exe-compiler-option.md) to create a console application.</span></span>  
  
 <span data-ttu-id="f71f1-110">[-out](./out-compiler-option.md) 옵션을 사용하여 지정하지 않으면 [Main](../../programming-guide/main-and-command-args/index.md) 메서드가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-110">Unless otherwise specified with the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="f71f1-111">명령줄에서 지정된 경우, 다음 **-out** 또는 [-target](./target-compiler-option.md) 옵션까지의 모든 파일이 Windows 프로그램을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-111">When specified at the command line, all files until the next **-out** or [-target](./target-compiler-option.md) option are used to create the Windows program.</span></span>  
  
 <span data-ttu-id="f71f1-112">.exe 파일로 컴파일되는 소스 코드 파일에 **Main** 메서드가 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-112">One and only one **Main** method is required in the source code files that are compiled into an .exe file.</span></span> <span data-ttu-id="f71f1-113">[-main](./main-compiler-option.md) 옵션을 사용하면 코드에 **Main** 메서드를 포함하는 클래스가 둘 이상 있는 경우 **Main** 메서드를 포함하는 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-113">The [-main](./main-compiler-option.md) option lets you specify which class contains the **Main** method, in cases where your code has more than one class with a **Main** method.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f71f1-114">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f71f1-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="f71f1-115">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="f71f1-116">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="f71f1-117">**출력 형식** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-117">Modify the **Output type** property.</span></span>  
  
 <span data-ttu-id="f71f1-118">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f71f1-118">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f71f1-119">예제</span><span class="sxs-lookup"><span data-stu-id="f71f1-119">Example</span></span>  
 <span data-ttu-id="f71f1-120">`in.cs`를 Windows 프로그램으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f71f1-120">Compile `in.cs` into a Windows program:</span></span>  
  
```console  
csc -target:winexe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f71f1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f71f1-121">See also</span></span>

- [<span data-ttu-id="f71f1-122">-target(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f71f1-122">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="f71f1-123">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f71f1-123">C# Compiler Options</span></span>](./index.md)
