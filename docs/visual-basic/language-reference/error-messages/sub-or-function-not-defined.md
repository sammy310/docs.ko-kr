---
title: Sub 또는 Function이 정의되지 않았습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 9eb13d943f9f1cffc984847f7339111e06f5aa6b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373929"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="cecc2-102">Sub 또는 Function이 정의되지 않았습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cecc2-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="cecc2-103">`Sub`또는를 `Function` 호출 하기 위해 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="cecc2-104">이 오류가 발생하는 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-104">Possible causes of this error include:</span></span>  
  
- <span data-ttu-id="cecc2-105">프로시저 이름의 철자가 틀린 경우</span><span class="sxs-lookup"><span data-stu-id="cecc2-105">Misspelling the procedure name.</span></span>  
  
- <span data-ttu-id="cecc2-106">**참조** 대화 상자에서 해당 프로젝트에 대 한 참조를 명시적으로 추가 하지 않고 다른 프로젝트에서 프로시저를 호출 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
- <span data-ttu-id="cecc2-107">호출 하는 프로시저에 표시 되지 않는 프로시저 지정</span><span class="sxs-lookup"><span data-stu-id="cecc2-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
- <span data-ttu-id="cecc2-108">지정 된 라이브러리 또는 코드 리소스에 없는 Windows DLL (동적 연결 라이브러리) 루틴 또는 Macintosh 코드 리소스 루틴을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cecc2-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cecc2-109">To correct this error</span></span>  
  
1. <span data-ttu-id="cecc2-110">프로시저 이름의 철자가 정확한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="cecc2-111">**참조** 대화 상자에서 호출 하려는 프로시저를 포함 하는 프로젝트의 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="cecc2-112">표시 되지 않으면 **찾아보기** 단추를 클릭 하 여 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="cecc2-113">프로젝트 이름 왼쪽의 확인란을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="cecc2-114">루틴의 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc2-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecc2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cecc2-115">See also</span></span>

- [<span data-ttu-id="cecc2-116">오류 유형</span><span class="sxs-lookup"><span data-stu-id="cecc2-116">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="cecc2-117">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="cecc2-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="cecc2-118">Sub 문</span><span class="sxs-lookup"><span data-stu-id="cecc2-118">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="cecc2-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="cecc2-119">Function Statement</span></span>](../statements/function-statement.md)
