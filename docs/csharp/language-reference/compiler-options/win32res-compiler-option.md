---
description: -win32res(C# 컴파일러 옵션)
title: -win32res(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: c220c78a6d2c3109402a20f0de40fe9665d6c730
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140817"
---
# <a name="-win32res-c-compiler-options"></a><span data-ttu-id="7c906-103">-win32res(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="7c906-103">-win32res (C# Compiler Options)</span></span>
<span data-ttu-id="7c906-104">**-win32res** 옵션은 출력 파일에 Win32 리소스를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-104">The **-win32res** option inserts a Win32 resource in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c906-105">구문</span><span class="sxs-lookup"><span data-stu-id="7c906-105">Syntax</span></span>  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="7c906-106">인수</span><span class="sxs-lookup"><span data-stu-id="7c906-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="7c906-107">출력 파일에 추가하려는 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-107">The resource file that you want to add to your output file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c906-108">설명</span><span class="sxs-lookup"><span data-stu-id="7c906-108">Remarks</span></span>  
 <span data-ttu-id="7c906-109">Win32 리소스 파일은 [리소스 컴파일러](resource-compiler-option.md)로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-109">A Win32 resource file can be created with the [Resource Compiler](resource-compiler-option.md).</span></span> <span data-ttu-id="7c906-110">리소스 컴파일러는 Visual C++ 프로그램을 컴파일할 때 실행되며 .rc 파일에서 .res 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-110">The Resource Compiler is invoked when you compile a Visual C++ program; a .res file is created from the .rc file.</span></span>  
  
 <span data-ttu-id="7c906-111">Win32 리소스는 파일 탐색기에서 애플리케이션을 식별하는 데 도움이 되는 버전 정보나 비트맵 (아이콘) 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-111">A Win32 resource can contain version or bitmap (icon) information that would help identify your application in the File Explorer.</span></span> <span data-ttu-id="7c906-112">**-win32res**를 지정하지 않으면 컴파일러에서 어셈블리 버전을 기반으로 하여 버전 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-112">If you do not specify **-win32res**, the compiler will generate version information based on the assembly version.</span></span>  
  
 <span data-ttu-id="7c906-113">.NET Framework 리소스 파일을(참조하려면) [-linkresource](./linkresource-compiler-option.md)를(첨부하려면) [-resource](./resource-compiler-option.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7c906-113">See [-linkresource](./linkresource-compiler-option.md) (to reference) or [-resource](./resource-compiler-option.md) (to attach) a .NET Framework resource file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="7c906-114">Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="7c906-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="7c906-115">프로젝트 **속성** 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="7c906-116">**애플리케이션** 속성 페이지를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-116">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="7c906-117">**리소스 파일** 단추를 클릭한 다음 콤보 상자를 사용하여 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-117">Click on the **Resource File** button and choose a file by using the combo box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c906-118">예제</span><span class="sxs-lookup"><span data-stu-id="7c906-118">Example</span></span>  
 <span data-ttu-id="7c906-119">`in.cs`를 컴파일하고 Win32 리소스 파일 `rf.res`를 첨부하여 `in.exe`를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7c906-119">Compile `in.cs` and attach a Win32 resource file `rf.res` to produce `in.exe`:</span></span>  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c906-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c906-120">See also</span></span>

- [<span data-ttu-id="7c906-121">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="7c906-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="7c906-122">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="7c906-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
