---
description: '자세한 정보: -nowin32manifest(Visual Basic)'
title: -nowin32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 3aa07ee26e47d48da69f1d1b34c8ec4643b7422e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100426722"
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="75ab2-103">-nowin32manifest(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75ab2-103">-nowin32manifest (Visual Basic)</span></span>

<span data-ttu-id="75ab2-104">실행 파일에 애플리케이션 매니페스트를 포함하지 않도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="75ab2-104">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ab2-105">구문</span><span class="sxs-lookup"><span data-stu-id="75ab2-105">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="75ab2-106">설명</span><span class="sxs-lookup"><span data-stu-id="75ab2-106">Remarks</span></span>  

 <span data-ttu-id="75ab2-107">이 옵션을 사용하는 경우 Win32 리소스 파일에서 또는 이후 빌드 단계 중에 애플리케이션 매니페스트를 제공하지 않으면 Windows Vista에서 애플리케이션에 가상화가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75ab2-107">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="75ab2-108">가상화에 대한 자세한 내용은 [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista)(Windows Vista의 ClickOnce 배포)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75ab2-108">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="75ab2-109">매니페스트 생성에 대한 자세한 내용은 [-win32manifest(Visual Basic)](win32manifest.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75ab2-109">For more information about manifest creation, see [-win32manifest (Visual Basic)](win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ab2-110">참조</span><span class="sxs-lookup"><span data-stu-id="75ab2-110">See also</span></span>

- [<span data-ttu-id="75ab2-111">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="75ab2-111">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="75ab2-112">프로젝트 디자이너, 애플리케이션 페이지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75ab2-112">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
