---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 286dd8bd9949b584cec38642f44ba9ac5e924732
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557179"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="23d65-102">-langversion(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23d65-102">-langversion (Visual Basic)</span></span>
<span data-ttu-id="23d65-103">컴파일러에서 지정된 Visual Basic 언어 버전에 포함된 구문만 허용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d65-104">구문</span><span class="sxs-lookup"><span data-stu-id="23d65-104">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="23d65-105">인수</span><span class="sxs-lookup"><span data-stu-id="23d65-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="23d65-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="23d65-106">Required.</span></span> <span data-ttu-id="23d65-107">컴파일하는 동안 사용할 언어 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="23d65-108">허용되는 값은 `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` 및 `latest`입니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-108">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` and `latest`.</span></span>

 <span data-ttu-id="23d65-109">`.0`를 부 버전으로 사용하여 전체 숫자를 지정할 수도 있습니다(예: `11.0`).</span><span class="sxs-lookup"><span data-stu-id="23d65-109">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="23d65-110">명령줄에서 `-langversion:?`을 지정하면 가능한 모든 값의 목록을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-110">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d65-111">설명</span><span class="sxs-lookup"><span data-stu-id="23d65-111">Remarks</span></span>  
 <span data-ttu-id="23d65-112">`-langversion` 옵션은 컴파일러에서 허용하는 구문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-112">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="23d65-113">예를 들어 언어 버전을 9.0으로 지정하면 컴파일러는 버전 10.0 이상에서만 유효한 구문에 대한 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-113">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="23d65-114">다른 버전의 .NET Framework를 대상으로 하는 애플리케이션을 개발할 때 이 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-114">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="23d65-115">예를 들어 .NET Framework 3.5를 대상으로 하는 경우 이 옵션을 사용하여 언어 버전 10.0의 구문을 사용하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-115">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="23d65-116">명령줄을 사용하여 `-langversion`을 직접 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-116">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="23d65-117">자세한 내용은 [특정 대상 .NET Framework 버전 지정](/visualstudio/ide/visual-studio-multi-targeting-overview)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23d65-117">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23d65-118">예제</span><span class="sxs-lookup"><span data-stu-id="23d65-118">Example</span></span>  
 <span data-ttu-id="23d65-119">다음 코드는 Visual Basic 9.0에 대한 `sample.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="23d65-119">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="23d65-120">참조</span><span class="sxs-lookup"><span data-stu-id="23d65-120">See also</span></span>

- [<span data-ttu-id="23d65-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="23d65-121">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="23d65-122">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="23d65-122">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
