---
title: 속성과 변수의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: 162bd71eaebdf55f6be89e0c5dce7acc1b975d79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403306"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="e66cb-102">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="e66cb-102">Differences Between Properties and Variables in Visual Basic</span></span>
<span data-ttu-id="e66cb-103">변수와 속성은 모두 액세스할 수 있는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="e66cb-104">그러나 저장소와 구현에는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="e66cb-105">variables</span><span class="sxs-lookup"><span data-stu-id="e66cb-105">Variables</span></span>  
 <span data-ttu-id="e66cb-106">*변수* 는 메모리 위치에 직접 대응 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="e66cb-107">단일 선언문을 사용 하 여 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="e66cb-108">변수는 프로시저 내에 정의 되 고 해당 프로시저 내 에서만 사용할 수 있는 *지역 변수*이거나 모듈, 클래스 또는 구조에 정의 되어 있지만 프로시저 내에서 정의 되지 않은 *멤버 변수일*수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="e66cb-109">멤버 변수는 *필드*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e66cb-110">속성</span><span class="sxs-lookup"><span data-stu-id="e66cb-110">Properties</span></span>  
 <span data-ttu-id="e66cb-111">*속성* 은 모듈, 클래스 또는 구조에 정의 된 데이터 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="e66cb-112">및 문 사이에 코드 블록을 사용 하 여 속성을 정의 `Property` `End Property` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="e66cb-113">코드 블록은 `Get` 프로시저, `Set` 프로시저 또는 둘 다를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="e66cb-114">이러한 프로시저를 *속성 프로시저* 또는 *속성 접근자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="e66cb-115">속성의 값을 검색 하거나 저장 하는 것 외에도 액세스 카운터를 업데이트 하는 등의 사용자 지정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="e66cb-116">차이점</span><span class="sxs-lookup"><span data-stu-id="e66cb-116">Differences</span></span>  
 <span data-ttu-id="e66cb-117">다음 표에서는 변수와 속성의 몇 가지 중요 한 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="e66cb-118">차이 가리키기</span><span class="sxs-lookup"><span data-stu-id="e66cb-118">Point of difference</span></span>|<span data-ttu-id="e66cb-119">변수</span><span class="sxs-lookup"><span data-stu-id="e66cb-119">Variable</span></span>|<span data-ttu-id="e66cb-120">속성</span><span class="sxs-lookup"><span data-stu-id="e66cb-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="e66cb-121">선언</span><span class="sxs-lookup"><span data-stu-id="e66cb-121">Declaration</span></span>|<span data-ttu-id="e66cb-122">단일 선언문</span><span class="sxs-lookup"><span data-stu-id="e66cb-122">Single declaration statement</span></span>|<span data-ttu-id="e66cb-123">코드 블록의 일련 문</span><span class="sxs-lookup"><span data-stu-id="e66cb-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="e66cb-124">구현</span><span class="sxs-lookup"><span data-stu-id="e66cb-124">Implementation</span></span>|<span data-ttu-id="e66cb-125">단일 저장소 위치</span><span class="sxs-lookup"><span data-stu-id="e66cb-125">Single storage location</span></span>|<span data-ttu-id="e66cb-126">실행 코드 (속성 프로시저)</span><span class="sxs-lookup"><span data-stu-id="e66cb-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="e66cb-127">스토리지</span><span class="sxs-lookup"><span data-stu-id="e66cb-127">Storage</span></span>|<span data-ttu-id="e66cb-128">변수의 값에 직접 연결</span><span class="sxs-lookup"><span data-stu-id="e66cb-128">Directly associated with variable's value</span></span>|<span data-ttu-id="e66cb-129">일반적으로 내부 저장소는 속성의 포함 하는 클래스 또는 모듈 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="e66cb-130">속성의 값이 저장 된 요소로 있을 수도 있고 없을 수도 있습니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e66cb-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="e66cb-131">실행 코드</span><span class="sxs-lookup"><span data-stu-id="e66cb-131">Executable code</span></span>|<span data-ttu-id="e66cb-132">없음</span><span class="sxs-lookup"><span data-stu-id="e66cb-132">None</span></span>|<span data-ttu-id="e66cb-133">하나 이상의 프로시저가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="e66cb-134">읽기 및 쓰기 권한</span><span class="sxs-lookup"><span data-stu-id="e66cb-134">Read and write access</span></span>|<span data-ttu-id="e66cb-135">읽기/쓰기 또는 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e66cb-135">Read/write or read-only</span></span>|<span data-ttu-id="e66cb-136">읽기/쓰기, 읽기 전용 또는 쓰기 전용</span><span class="sxs-lookup"><span data-stu-id="e66cb-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="e66cb-137">사용자 지정 작업 (값을 허용 하거나 반환 하는 것 외에)</span><span class="sxs-lookup"><span data-stu-id="e66cb-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="e66cb-138">가능하지 않음</span><span class="sxs-lookup"><span data-stu-id="e66cb-138">Not possible</span></span>|<span data-ttu-id="e66cb-139">속성 값을 설정 하거나 검색 하는 과정에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="e66cb-140"><sup>1</sup> 변수와 달리 속성의 값은 저장소의 단일 항목에 직접적으로 해당 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="e66cb-141">저장소는 편리 하거나 보안을 위해 여러 조각으로 분할 될 수 있으며, 값은 암호화 된 형식으로 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="e66cb-142">이러한 경우 프로시저는 `Get` 조각을 조합 하거나 저장 된 값의 암호를 해독 하 고 `Set` 새 값을 암호화 하거나이를 구성 저장소로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="e66cb-143">속성 값은 하루와 같이 임시 일 수 있으며, `Get` 이 경우 프로시저는 속성에 액세스할 때마다 즉석에서이를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="e66cb-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e66cb-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e66cb-144">See also</span></span>

- [<span data-ttu-id="e66cb-145">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="e66cb-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e66cb-146">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="e66cb-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e66cb-147">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e66cb-147">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="e66cb-148">Dim 문</span><span class="sxs-lookup"><span data-stu-id="e66cb-148">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="e66cb-149">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="e66cb-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="e66cb-150">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="e66cb-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="e66cb-151">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="e66cb-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="e66cb-152">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="e66cb-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="e66cb-153">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="e66cb-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="e66cb-154">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="e66cb-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
