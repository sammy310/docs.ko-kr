---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 8dfd830e4c7ed97c8813da4ad310ee59b26f44f8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90868807"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="85f37-102">Ansi(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85f37-102">Ansi (Visual Basic)</span></span>

<span data-ttu-id="85f37-103">선언 되는 외부 프로시저의 이름에 관계 없이 모든 문자열을 ANSI(American National Standards Institute) (ANSI) 값으로 마샬링하 Visual Basic 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="85f37-104">프로젝트 외부에서 정의 된 프로시저를 호출 하는 경우 Visual Basic 컴파일러는 프로시저를 올바르게 호출 하는 데 필요한 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="85f37-105">이 정보에는 프로시저가 있는 위치, 식별 방법, 호출 시퀀스 및 반환 형식, 사용 하는 문자열 문자 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="85f37-106">[Declare 문은](../statements/declare-statement.md) 외부 프로시저에 대 한 참조를 만들고이 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="85f37-107">`charsetmodifier` `Declare` 문의 부분은 외부 프로시저를 호출 하는 동안 문자열을 마샬링하기 위한 문자 집합 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="85f37-108">외부 파일에서 외부 프로시저 이름을 검색 Visual Basic는 방법에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="85f37-109">`Ansi`한정자는 Visual Basic 모든 문자열을 ANSI 값으로 마샬링하고 검색 하는 동안 해당 이름을 수정 하지 않고 프로시저를 조회 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="85f37-110">문자 집합 한정자가 지정 되지 않은 경우 `Ansi` 가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f37-111">설명</span><span class="sxs-lookup"><span data-stu-id="85f37-111">Remarks</span></span>  

 <span data-ttu-id="85f37-112">`Ansi`이 컨텍스트에서는 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="85f37-113">Declare 문</span><span class="sxs-lookup"><span data-stu-id="85f37-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="85f37-114">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="85f37-114">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="85f37-115">이 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85f37-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f37-116">참조</span><span class="sxs-lookup"><span data-stu-id="85f37-116">See also</span></span>

- [<span data-ttu-id="85f37-117">자동</span><span class="sxs-lookup"><span data-stu-id="85f37-117">Auto</span></span>](auto.md)
- [<span data-ttu-id="85f37-118">유니코드</span><span class="sxs-lookup"><span data-stu-id="85f37-118">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="85f37-119">키워드</span><span class="sxs-lookup"><span data-stu-id="85f37-119">Keywords</span></span>](../keywords/index.md)
