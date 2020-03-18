---
title: -main(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 6c842abc1423e7ee0d98b71392e02410c6cf9172
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602730"
---
# <a name="-main-c-compiler-options"></a><span data-ttu-id="9f8e5-102">-main(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="9f8e5-102">-main (C# Compiler Options)</span></span>
<span data-ttu-id="9f8e5-103">이 옵션은 둘 이상의 클래스에 **Main** 메서드가 포함된 경우 프로그램에 대한 진입점을 포함하는 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-103">This option specifies the class that contains the entry point to the program, if more than one class contains a **Main** method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f8e5-104">Syntax</span></span>  
  
```console  
-main:class  
```  
  
## <a name="arguments"></a><span data-ttu-id="9f8e5-105">인수</span><span class="sxs-lookup"><span data-stu-id="9f8e5-105">Arguments</span></span>  
 `class`  
 <span data-ttu-id="9f8e5-106">**Main** 메서드를 포함하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-106">The type that contains the **Main** method.</span></span>  
 <span data-ttu-id="9f8e5-107">제공된 클래스 이름은 완전히 정규화되어야 하며, 클래스를 포함하는 전체 네임스페이스와 클래스 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-107">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="9f8e5-108">예를 들어 `Main` 메서드가 `Program` 네임스페이스의 `MyApplication.Core` 클래스 내에 있는 경우 컴파일러 옵션은 `-main:MyApplication.Core.Program`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-108">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9f8e5-109">설명</span><span class="sxs-lookup"><span data-stu-id="9f8e5-109">Remarks</span></span>  
 <span data-ttu-id="9f8e5-110">컴파일에 [Main](../../programming-guide/main-and-command-args/index.md) 메서드가 있는 형식이 둘 이상 포함된 경우 프로그램에 대한 진입점으로 사용할 **Main** 메서드를 포함하는 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-110">If your compilation includes more than one type with a [Main](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the **Main** method that you want to use as the entry point into the program.</span></span>  
  
 <span data-ttu-id="9f8e5-111">이 옵션은 .exe 파일을 컴파일할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-111">This option is for use when compiling an .exe file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="9f8e5-112">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9f8e5-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="9f8e5-113">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="9f8e5-114">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-114">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="9f8e5-115">**시작 개체** 속성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-115">Modify the **Startup object** property.</span></span>  
  
     <span data-ttu-id="9f8e5-116">프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-116">To set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f8e5-117">예제</span><span class="sxs-lookup"><span data-stu-id="9f8e5-117">Example</span></span>  
 <span data-ttu-id="9f8e5-118">`t2.cs`Main`t3.cs` 메서드가 **에 있다고 지정하여**  및 `Test2`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9f8e5-118">Compile `t2.cs` and `t3.cs`, specifying that the **Main** method will be found in `Test2`:</span></span>  
  
```console  
csc t2.cs t3.cs -main:Test2  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f8e5-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f8e5-119">See also</span></span>

- [<span data-ttu-id="9f8e5-120">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="9f8e5-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="9f8e5-121">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="9f8e5-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
