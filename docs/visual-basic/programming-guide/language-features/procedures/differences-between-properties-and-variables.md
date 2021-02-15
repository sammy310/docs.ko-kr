---
description: '자세히 알아보기: Visual Basic 속성과 변수 간의 차이점'
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
ms.openlocfilehash: 6118d37616f3df1f21dda8e3a6392b6a6f37a24e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464718"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="d395f-103">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="d395f-103">Differences Between Properties and Variables in Visual Basic</span></span>

<span data-ttu-id="d395f-104">변수와 속성은 모두 액세스할 수 있는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-104">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="d395f-105">그러나 저장소와 구현에는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-105">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="d395f-106">변수</span><span class="sxs-lookup"><span data-stu-id="d395f-106">Variables</span></span>  

 <span data-ttu-id="d395f-107">*변수* 는 메모리 위치에 직접 대응 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-107">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="d395f-108">단일 선언문을 사용 하 여 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-108">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="d395f-109">변수는 프로시저 내에 정의 되 고 해당 프로시저 내 에서만 사용할 수 있는 *지역 변수* 이거나 모듈, 클래스 또는 구조에 정의 되어 있지만 프로시저 내에서 정의 되지 않은 *멤버 변수일* 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-109">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="d395f-110">멤버 변수는 *필드* 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-110">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d395f-111">속성</span><span class="sxs-lookup"><span data-stu-id="d395f-111">Properties</span></span>  

 <span data-ttu-id="d395f-112">*속성* 은 모듈, 클래스 또는 구조에 정의 된 데이터 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-112">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="d395f-113">및 문 사이에 코드 블록을 사용 하 여 속성을 정의 `Property` `End Property` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-113">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="d395f-114">코드 블록은 `Get` 프로시저, `Set` 프로시저 또는 둘 다를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-114">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="d395f-115">이러한 프로시저를 *속성 프로시저* 또는 *속성 접근자* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-115">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="d395f-116">속성의 값을 검색 하거나 저장 하는 것 외에도 액세스 카운터를 업데이트 하는 등의 사용자 지정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-116">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="d395f-117">차이점</span><span class="sxs-lookup"><span data-stu-id="d395f-117">Differences</span></span>  

 <span data-ttu-id="d395f-118">다음 표에서는 변수와 속성의 몇 가지 중요 한 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-118">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="d395f-119">차이 가리키기</span><span class="sxs-lookup"><span data-stu-id="d395f-119">Point of difference</span></span>|<span data-ttu-id="d395f-120">변수</span><span class="sxs-lookup"><span data-stu-id="d395f-120">Variable</span></span>|<span data-ttu-id="d395f-121">속성</span><span class="sxs-lookup"><span data-stu-id="d395f-121">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="d395f-122">선언</span><span class="sxs-lookup"><span data-stu-id="d395f-122">Declaration</span></span>|<span data-ttu-id="d395f-123">단일 선언문</span><span class="sxs-lookup"><span data-stu-id="d395f-123">Single declaration statement</span></span>|<span data-ttu-id="d395f-124">코드 블록의 일련 문</span><span class="sxs-lookup"><span data-stu-id="d395f-124">Series of statements in a code block</span></span>|  
|<span data-ttu-id="d395f-125">구현</span><span class="sxs-lookup"><span data-stu-id="d395f-125">Implementation</span></span>|<span data-ttu-id="d395f-126">단일 저장소 위치</span><span class="sxs-lookup"><span data-stu-id="d395f-126">Single storage location</span></span>|<span data-ttu-id="d395f-127">실행 코드 (속성 프로시저)</span><span class="sxs-lookup"><span data-stu-id="d395f-127">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="d395f-128">스토리지</span><span class="sxs-lookup"><span data-stu-id="d395f-128">Storage</span></span>|<span data-ttu-id="d395f-129">변수의 값에 직접 연결</span><span class="sxs-lookup"><span data-stu-id="d395f-129">Directly associated with variable's value</span></span>|<span data-ttu-id="d395f-130">일반적으로 내부 저장소는 속성의 포함 하는 클래스 또는 모듈 외부에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-130">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="d395f-131">속성의 값이 저장 된 요소로 있을 수도 있고 없을 수도 있습니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d395f-131">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="d395f-132">실행 코드</span><span class="sxs-lookup"><span data-stu-id="d395f-132">Executable code</span></span>|<span data-ttu-id="d395f-133">없음</span><span class="sxs-lookup"><span data-stu-id="d395f-133">None</span></span>|<span data-ttu-id="d395f-134">하나 이상의 프로시저가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-134">Must have at least one procedure</span></span>|  
|<span data-ttu-id="d395f-135">읽기 및 쓰기 권한</span><span class="sxs-lookup"><span data-stu-id="d395f-135">Read and write access</span></span>|<span data-ttu-id="d395f-136">읽기/쓰기 또는 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="d395f-136">Read/write or read-only</span></span>|<span data-ttu-id="d395f-137">읽기/쓰기, 읽기 전용 또는 쓰기 전용</span><span class="sxs-lookup"><span data-stu-id="d395f-137">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="d395f-138">사용자 지정 작업 (값을 허용 하거나 반환 하는 것 외에)</span><span class="sxs-lookup"><span data-stu-id="d395f-138">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="d395f-139">가능하지 않음</span><span class="sxs-lookup"><span data-stu-id="d395f-139">Not possible</span></span>|<span data-ttu-id="d395f-140">속성 값을 설정 하거나 검색 하는 과정에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-140">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="d395f-141"><sup>1</sup> 변수와 달리 속성의 값은 저장소의 단일 항목에 직접적으로 해당 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-141"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="d395f-142">저장소는 편리 하거나 보안을 위해 여러 조각으로 분할 될 수 있으며, 값은 암호화 된 형식으로 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-142">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="d395f-143">이러한 경우 프로시저는 `Get` 조각을 조합 하거나 저장 된 값의 암호를 해독 하 고 `Set` 새 값을 암호화 하거나이를 구성 저장소로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-143">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="d395f-144">속성 값은 하루와 같이 임시 일 수 있으며, `Get` 이 경우 프로시저는 속성에 액세스할 때마다 즉석에서이를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d395f-144">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d395f-145">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d395f-145">See also</span></span>

- [<span data-ttu-id="d395f-146">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="d395f-146">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d395f-147">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="d395f-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d395f-148">Property Statement</span><span class="sxs-lookup"><span data-stu-id="d395f-148">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="d395f-149">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d395f-149">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="d395f-150">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="d395f-150">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="d395f-151">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="d395f-151">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="d395f-152">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="d395f-152">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="d395f-153">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="d395f-153">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="d395f-154">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="d395f-154">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="d395f-155">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="d395f-155">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
