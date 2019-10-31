---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 5f59f1c4c269a52131a324bbd2bfbe817ab794a4
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197095"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="fca8b-102">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fca8b-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="fca8b-103">컴파일러가 지정 된 Visual Basic 언어 버전에 포함 된 구문만 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fca8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="fca8b-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="fca8b-105">인수</span><span class="sxs-lookup"><span data-stu-id="fca8b-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="fca8b-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="fca8b-106">Required.</span></span> <span data-ttu-id="fca8b-107">컴파일하는 동안 사용할 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="fca8b-108">허용 되는 값은 `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default`, `latest`입니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="fca8b-109">`.0`를 사용 하 여 전체 숫자를 지정할 수도 있습니다 (예: `11.0`).</span><span class="sxs-lookup"><span data-stu-id="fca8b-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="fca8b-110">명령줄에서 `-langversion:?`를 지정 하 여 가능한 모든 값 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fca8b-111">주의</span><span class="sxs-lookup"><span data-stu-id="fca8b-111">Remarks</span></span>  
 <span data-ttu-id="fca8b-112">`-langversion` 옵션은 컴파일러가 허용 하는 구문을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="fca8b-113">예를 들어 언어 버전을 9.0로 지정 하는 경우 컴파일러는 버전 10.0 이상 에서만 유효한 구문에 대 한 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="fca8b-114">.NET Framework의 다른 버전을 대상으로 하는 응용 프로그램을 개발할 때이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="fca8b-115">예를 들어 .NET Framework 3.5를 대상으로 하는 경우이 옵션을 사용 하 여 언어 버전 10.0에서 구문을 사용 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="fca8b-116">명령줄을 사용 하 여 `-langversion`를 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="fca8b-117">자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/visual-studio-multi-targeting-overview)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fca8b-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fca8b-118">예제</span><span class="sxs-lookup"><span data-stu-id="fca8b-118">Example</span></span>  
 <span data-ttu-id="fca8b-119">다음 코드는 Visual Basic 9.0에 대 한 `sample.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="fca8b-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fca8b-120">참조</span><span class="sxs-lookup"><span data-stu-id="fca8b-120">See also</span></span>

- [<span data-ttu-id="fca8b-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fca8b-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fca8b-122">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fca8b-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="fca8b-123">특정 대상 .NET Framework 버전 지정</span><span class="sxs-lookup"><span data-stu-id="fca8b-123">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/visual-studio-multi-targeting-overview)
