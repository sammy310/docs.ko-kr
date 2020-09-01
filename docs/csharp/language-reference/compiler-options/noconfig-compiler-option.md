---
description: -noconfig(C# 컴파일러 옵션)
title: -noconfig(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 26d0680743ccc3af26a0e81eeec9cd2fc0d693af
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125230"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="e876d-103">-noconfig(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="e876d-103">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="e876d-104">**-noconfig** 옵션은 csc.exe 파일과 동일한 디렉터리에 있고 여기서 로드되는 csc.rsp 파일로 컴파일하지 않도록 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-104">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e876d-105">구문</span><span class="sxs-lookup"><span data-stu-id="e876d-105">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="e876d-106">설명</span><span class="sxs-lookup"><span data-stu-id="e876d-106">Remarks</span></span>  
 <span data-ttu-id="e876d-107">csc.rsp 파일은 .NET Framework와 함께 제공되는 모든 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-107">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="e876d-108">Visual Studio .NET 개발 환경에 포함된 실제 참조는 프로젝트 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-108">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="e876d-109">csc.rsp 파일을 수정하여 **-noconfig** 옵션을 제외하고 csc.exe를 사용하여 명령줄에서 컴파일할 때마다 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-109">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="e876d-110">컴파일러는 **csc** 명령에 마지막으로 전달된 옵션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-110">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="e876d-111">따라서 명령줄의 모든 옵션은 csc.rsp 파일에 있는 동일한 옵션의 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-111">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="e876d-112">컴파일러가 csc.rsp 파일의 설정을 찾아서 사용하지 않도록 하려면 **-noconfig**를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-112">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="e876d-113">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e876d-113">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e876d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e876d-114">See also</span></span>

- [<span data-ttu-id="e876d-115">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="e876d-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e876d-116">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="e876d-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
