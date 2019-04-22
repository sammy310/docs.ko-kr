---
title: DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816904"
---
# <a name="error-in-loading-dll-visual-basic"></a><span data-ttu-id="cb06d-102">DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cb06d-102">Error in loading DLL (Visual Basic)</span></span>
<span data-ttu-id="cb06d-103">동적 연결 라이브러리 (DLL)는에 지정 된 라이브러리는 `Lib` 절을 `Declare` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-103">A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement.</span></span> <span data-ttu-id="cb06d-104">이 오류의 가능한 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-104">Possible causes for this error include:</span></span>  
  
-   <span data-ttu-id="cb06d-105">파일을 실행 하는 DLL 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-105">The file is not DLL executable.</span></span>  
  
-   <span data-ttu-id="cb06d-106">Microsoft Windows DLL 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-106">The file is not a Microsoft Windows DLL.</span></span>  
  
-   <span data-ttu-id="cb06d-107">DLL에 들어 있지 않은 다른 DLL 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-107">The DLL references another DLL that is not present.</span></span>  
  
-   <span data-ttu-id="cb06d-108">DLL 또는 참조 된 DLL의 경로에 지정 된 디렉터리 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-108">The DLL or referenced DLL is not in a directory specified in the path.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb06d-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cb06d-109">To correct this error</span></span>  
  
-   <span data-ttu-id="cb06d-110">파일 소스 텍스트 파일 및 따라서 이면 컴파일 및 DLL 실행 폼에 연결 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-110">If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.</span></span>  
  
-   <span data-ttu-id="cb06d-111">Microsoft Windows DLL 파일이 없는 경우 해당 하는 Microsoft Windows를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-111">If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.</span></span>  
  
-   <span data-ttu-id="cb06d-112">DLL이 존재 하지 않는 다른 DLL을 참조 하는 경우 참조 된 DLL 가져오고 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-112">If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.</span></span>  
  
-   <span data-ttu-id="cb06d-113">DLL 또는 참조 된 DLL의 경로 지정 된 디렉터리에 없으면 DLL 참조 된 디렉터리로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb06d-113">If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb06d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb06d-114">See also</span></span>

- [<span data-ttu-id="cb06d-115">Declare 문</span><span class="sxs-lookup"><span data-stu-id="cb06d-115">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
