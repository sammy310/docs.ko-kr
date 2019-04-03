---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839725"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="01b0c-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01b0c-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="01b0c-103">컴파일러가 지정된 된 Visual Basic 언어 버전에 포함 된 구문만 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b0c-104">구문</span><span class="sxs-lookup"><span data-stu-id="01b0c-104">Syntax</span></span>  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="01b0c-105">인수</span><span class="sxs-lookup"><span data-stu-id="01b0c-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="01b0c-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="01b0c-106">Required.</span></span> <span data-ttu-id="01b0c-107">컴파일하는 동안 사용할 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="01b0c-108">허용 되는 값은 `9`, `10`, `11`, `12`, `14`를 `15`, `15.3`를 `15.5`를 `default` 및 `latest`합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="01b0c-109">전체 숫자 하나라도 지정할 수 있습니다 사용 하 여 `.0` 부 버전, 예를 들어 `11.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="01b0c-110">모든 가능한 값 목록을 지정 하 여 보이는 `-langversion:?` 명령줄에서.</span><span class="sxs-lookup"><span data-stu-id="01b0c-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01b0c-111">설명</span><span class="sxs-lookup"><span data-stu-id="01b0c-111">Remarks</span></span>  
 <span data-ttu-id="01b0c-112">`-langversion` 옵션 컴파일러에서는 허용 되는 구문을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="01b0c-113">예를 들어 언어 버전 9.0 인지를 지정 하면 컴파일러 이상 10.0 버전에만 유효는 구문에 대 한 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="01b0c-114">해당 대상 다른 버전의.NET Framework 응용 프로그램을 개발 하는 경우이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="01b0c-115">예를 들어,.NET Framework 3.5를 대상으로 하는 경우 언어 버전 10.0에서에서 구문을 사용 하는지 확인 하려면이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="01b0c-116">설정할 수 있습니다 `-langversion` 직접 명령줄을 사용 해야만 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="01b0c-117">자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01b0c-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b0c-118">예제</span><span class="sxs-lookup"><span data-stu-id="01b0c-118">Example</span></span>  
 <span data-ttu-id="01b0c-119">다음 코드에서는 `sample.vb` Visual Basic 9.0에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="01b0c-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="01b0c-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="01b0c-120">See also</span></span>

- [<span data-ttu-id="01b0c-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="01b0c-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="01b0c-122">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="01b0c-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="01b0c-123">특정 대상 .NET Framework 버전 지정</span><span class="sxs-lookup"><span data-stu-id="01b0c-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
