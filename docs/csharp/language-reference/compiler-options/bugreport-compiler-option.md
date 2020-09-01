---
description: -bugreport(C# 컴파일러 옵션)
title: -bugreport(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 2c358b2dda400f6077ffb5ba1dfc8e6e1127fa52
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125997"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="5d712-103">-bugreport(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="5d712-103">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="5d712-104">나중에 분석하기 위해 파일에 디버그 정보를 포함하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-104">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d712-105">구문</span><span class="sxs-lookup"><span data-stu-id="5d712-105">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="5d712-106">인수</span><span class="sxs-lookup"><span data-stu-id="5d712-106">Arguments</span></span>  
 `file`  
 <span data-ttu-id="5d712-107">버그 보고서를 포함하려는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-107">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d712-108">설명</span><span class="sxs-lookup"><span data-stu-id="5d712-108">Remarks</span></span>  
 <span data-ttu-id="5d712-109">**-bugreport** 옵션은 `file`에 다음 정보를 포함하도록 지정합니다:</span><span class="sxs-lookup"><span data-stu-id="5d712-109">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
- <span data-ttu-id="5d712-110">컴파일에 포함된 모든 소스 코드 파일의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-110">A copy of all source code files in the compilation.</span></span>  
  
- <span data-ttu-id="5d712-111">컴파일에 사용된 컴파일러 옵션 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-111">A listing of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="5d712-112">컴파일러, 런타임 및 운영 체제에 대한 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-112">Version information about your compiler, run time, and operating system.</span></span>  
  
- <span data-ttu-id="5d712-113">.NET Framework 및 SDK와 함께 제공되는 어셈블리를 제외하고 16진수로 저장된 참조된 어셈블리 및 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-113">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
- <span data-ttu-id="5d712-114">컴파일러 출력입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="5d712-114">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="5d712-115">메시지가 표시되는 문제에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-115">A description of the problem, which you will be prompted for.</span></span>  
  
- <span data-ttu-id="5d712-116">메시지가 표시되는 문제 해결 방법에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-116">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="5d712-117">**-errorreport:prompt** 또는 **-errorreport:send**와 함께 이 옵션을 사용할 경우 파일의 정보가 Microsoft Corporation에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-117">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="5d712-118">모든 소스 코드 파일의 복사본이 `file`에 저장되기 때문에 최대한 짧은 프로그램으로 의심스러운 코드 결함을 재현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-118">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="5d712-119">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-119">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="5d712-120">생성된 파일 내용에 의해 소스 코드가 노출되어, 의도하지 않게 정보가 공개될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d712-120">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d712-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d712-121">See also</span></span>

- [<span data-ttu-id="5d712-122">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="5d712-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="5d712-123">-errorreport(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="5d712-123">-errorreport (C# Compiler Options)</span></span>](./errorreport-compiler-option.md)
- [<span data-ttu-id="5d712-124">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="5d712-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
