---
title: -target:appcontainerexe(C# 컴파일러 옵션)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: 64661e72f9efe190606cadd93558678cb849e8cc
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204534"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a><span data-ttu-id="b3070-102">-target:appcontainerexe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="b3070-102">-target:appcontainerexe (C# Compiler Options)</span></span>
<span data-ttu-id="b3070-103">**-target:appcontainerexe** 컴파일러 옵션을 사용하면 컴파일러는 앱 컨테이너에서 실행해야 하는 Windows 실행 파일(.exe)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-103">If you use the **-target:appcontainerexe** compiler option, the compiler creates a Windows executable (.exe) file that must be run in an app container.</span></span> <span data-ttu-id="b3070-104">이 옵션은 [-target:winexe](./target-winexe-compiler-option.md)와 같지만, Windows 8.x 스토어 앱을 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-104">This option is equivalent to [-target:winexe](./target-winexe-compiler-option.md) but is designed for Windows 8.x Store apps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3070-105">구문</span><span class="sxs-lookup"><span data-stu-id="b3070-105">Syntax</span></span>  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a><span data-ttu-id="b3070-106">설명</span><span class="sxs-lookup"><span data-stu-id="b3070-106">Remarks</span></span>  
 <span data-ttu-id="b3070-107">이 옵션은 앱이 앱 컨테이너에서 실행되도록 하기 위해 PE([이식 가능 파일](/windows/desktop/Debug/pe-format))에 비트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-107">To require the app to run in an app container, this option sets a bit in the [Portable Executable](/windows/desktop/Debug/pe-format) (PE) file.</span></span> <span data-ttu-id="b3070-108">해당 비트가 설정된 경우 CreateProcess 메서드가 응용 프로그램 밖에서 실행 파일을 실행하려고 시도하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-108">When that bit is set, an error occurs if the CreateProcess method tries to launch the executable file outside an app container.</span></span>  
  
 <span data-ttu-id="b3070-109">[-out](./out-compiler-option.md) 옵션을 사용하지 않으면 [Main](../../programming-guide/main-and-command-args/index.md) 메서드가 포함된 입력 파일의 이름이 출력 파일의 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-109">Unless you use the [-out](./out-compiler-option.md) option, the output file name takes the name of the input file that contains the [Main](../../programming-guide/main-and-command-args/index.md) method.</span></span>  
  
 <span data-ttu-id="b3070-110">이 옵션을 명령 프롬프트에서 지정하면 실행 파일을 만드는 데 다음 **-out** 또는 **-target** 옵션까지의 모든 파일이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-110">When you specify this option at a command prompt, all files until the next **-out** or **-target** option are used to create the executable file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a><span data-ttu-id="b3070-111">IDE에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="b3070-111">To set this compiler option in the IDE</span></span>  
  
1. <span data-ttu-id="b3070-112">**솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-112">In **Solution Explorer**, open the shortcut menu for your project, and then choose **Properties**.</span></span>  
  
2. <span data-ttu-id="b3070-113">**애플리케이션** 탭의 **출력 형식** 목록에서 **Windows 스토어 앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-113">On the **Application** tab, in the **Output type** list, choose **Windows Store App**.</span></span>  
  
     <span data-ttu-id="b3070-114">이 옵션은 Windows 8.x 스토어 앱 템플릿에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-114">This option is available only for Windows 8.x Store app templates.</span></span>  
  
 <span data-ttu-id="b3070-115">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3070-115">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3070-116">예</span><span class="sxs-lookup"><span data-stu-id="b3070-116">Example</span></span>  
 <span data-ttu-id="b3070-117">다음 명령은 `filename.cs`를 응용 프로그램 컨테이너에서만 실행할 수 있는 Windows 실행 파일로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b3070-117">The following command compiles `filename.cs` into a Windows executable file that can be run only in an app container.</span></span>  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3070-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3070-118">See also</span></span>

- [<span data-ttu-id="b3070-119">-target(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="b3070-119">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="b3070-120">-target:winexe(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="b3070-120">-target:winexe (C# Compiler Options)</span></span>](./target-winexe-compiler-option.md)
- [<span data-ttu-id="b3070-121">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="b3070-121">C# Compiler Options</span></span>](./index.md)
