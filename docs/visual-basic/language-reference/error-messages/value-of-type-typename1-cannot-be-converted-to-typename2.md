---
title: "'<typename1>' 형식의 값을 '<typename2>'(으)로 변환할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829027"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="ae400-102">형식의 값 '\<typename1 >'로 변환할 수 없습니다 '\<typename2 >'</span><span class="sxs-lookup"><span data-stu-id="ae400-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="ae400-103">형식의 값 '\<typename1 >'로 변환할 수 없습니다 '\<typename2 >'입니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="ae400-104">형식 불일치 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문일 수 있습니다 '\<assemblyname >'입니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="ae400-105">에 대 한 파일 참조를 바꿔 보십시오 '\<파일 경로 >' 프로젝트에서 '\<projectname1 >'에 대 한 프로젝트 참조를 사용 하 여 '\<projectname2 >'입니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="ae400-106">프로젝트의 프로젝트 참조와 파일 참조는 있는 경우에서 컴파일러는 형식 간에 변환할 수는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="ae400-107">다음 의사 코드에서는이 오류를 생성할 수 있는 위험한 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="ae400-108">프로젝트 `P1` 프로젝트를 통해 간접 프로젝트 참조를 사용 하면 `P2` 프로젝트에 `P3`, 및에 대 한 파일을 직접 참조도 `P3`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="ae400-109">선언의 `commonObject` 에 대 한 파일 참조를 사용 하 여 `P3`를 호출 하는 동안 `P2.getCommonClass` 에 대 한 프로젝트 참조를 사용 하 여 `P3`입니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="ae400-110">이런에서 문제는 파일 참조의 출력 파일에 대 한 이름과 파일 경로 지정 하는지 `P3` (일반적으로 p3.dll) 프로젝트 참조 소스 프로젝트를 식별 하는 동안 (`P3`) 프로젝트 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="ae400-111">이 인해 컴파일러 보장할 수 없습니다 형식 `P3.commonClass` 두 개의 다른 참조를 통해 동일한 소스 코드에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="ae400-112">이 상황은 일반적으로 발생 경우 프로젝트 참조와 파일 참조가 섞여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="ae400-113">앞의 그림에서 문제가 발생 하지 않습니다 `P1` 에 대 한 직접 프로젝트 참조 `P3` 파일 참조를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="ae400-114">**오류 ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="ae400-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae400-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ae400-115">To correct this error</span></span>  
  
-   <span data-ttu-id="ae400-116">프로젝트 참조에 대 한 파일 참조를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae400-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae400-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae400-117">See also</span></span>

- [<span data-ttu-id="ae400-118">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="ae400-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="ae400-119">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="ae400-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
