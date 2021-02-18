---
description: '자세한 정보: -nologo(Visual Basic)'
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 370889fbd5d4e499ba27ff8bee4adc16a7a71876
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434890"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="71b8f-103">-nologo(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71b8f-103">-nologo (Visual Basic)</span></span>

<span data-ttu-id="71b8f-104">컴파일하는 동안 저작권 배너 및 정보 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b8f-104">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b8f-105">구문</span><span class="sxs-lookup"><span data-stu-id="71b8f-105">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="71b8f-106">설명</span><span class="sxs-lookup"><span data-stu-id="71b8f-106">Remarks</span></span>  

 <span data-ttu-id="71b8f-107">`-nologo`를 지정하면 컴파일러에 저작권 배너가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b8f-107">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="71b8f-108">기본적으로 `-nologo`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b8f-108">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71b8f-109">Visual Studio 개발 환경 내에서는 `-nologo` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b8f-109">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71b8f-110">예제</span><span class="sxs-lookup"><span data-stu-id="71b8f-110">Example</span></span>  

 <span data-ttu-id="71b8f-111">다음 코드는 `T2.vb`를 컴파일하고 저작권 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b8f-111">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="71b8f-112">참조</span><span class="sxs-lookup"><span data-stu-id="71b8f-112">See also</span></span>

- [<span data-ttu-id="71b8f-113">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="71b8f-113">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="71b8f-114">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="71b8f-114">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
