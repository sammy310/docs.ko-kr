---
title: "'<propertyname>' 속성이 일부 코드 경로에 대해서만 값을 반환합니다."
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 0736e2cbcdea1422d40161c88f898d487f72e3bc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162390"
---
# <a name="bc42107-property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="87ee3-102">BC42107: ' \<propertyname> ' 속성이 일부 코드 경로에 대해서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-102">BC42107: Property '\<propertyname>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="87ee3-103">' \<propertyname> ' 속성이 일부 코드 경로에 대해서만 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="87ee3-104">이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-104">A null reference exception could occur at run time when the result is used.</span></span>

<span data-ttu-id="87ee3-105">속성 `Get` 프로시저의 코드를 통해 값을 반환 하지 않는 경로가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>

 <span data-ttu-id="87ee3-106">다음 방법 중 하나를 통해 속성 프로시저에서 값을 반환할 수 있습니다 `Get` .</span><span class="sxs-lookup"><span data-stu-id="87ee3-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>

- <span data-ttu-id="87ee3-107">속성 이름에 값을 할당 한 다음 `Exit Property` 문을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>

- <span data-ttu-id="87ee3-108">속성 이름에 값을 할당 한 다음 `End Get` 문을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>

- <span data-ttu-id="87ee3-109">[반환 문에](../statements/return-statement.md)값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-109">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>

<span data-ttu-id="87ee3-110">컨트롤이 또는로 전달 `Exit Property` `End Get` 되 고 속성 이름에 값을 할당 하지 않은 경우 `Get` 프로시저는 속성 데이터 형식의 기본값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="87ee3-111">자세한 내용은 [함수 문의](../statements/function-statement.md)"Behavior"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="87ee3-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>

<span data-ttu-id="87ee3-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-112">By default, this message is a warning.</span></span> <span data-ttu-id="87ee3-113">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87ee3-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="87ee3-114">**오류 ID:** BC42107</span><span class="sxs-lookup"><span data-stu-id="87ee3-114">**Error ID:** BC42107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="87ee3-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="87ee3-115">To correct this error</span></span>

- <span data-ttu-id="87ee3-116">제어 흐름 논리를 확인 하 고 반환을 발생 시키는 모든 문 앞에 값을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ee3-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>

  <span data-ttu-id="87ee3-117">항상 문을 사용 하는 경우 프로시저의 모든 반환에서 값을 반환 하도록 보장 하는 것이 더 쉽습니다 `Return` .</span><span class="sxs-lookup"><span data-stu-id="87ee3-117">It's easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="87ee3-118">이 작업을 수행 하는 경우 앞의 마지막 문이 문 이어야 합니다 `End Get` `Return` .</span><span class="sxs-lookup"><span data-stu-id="87ee3-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="87ee3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87ee3-119">See also</span></span>

- [<span data-ttu-id="87ee3-120">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="87ee3-120">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="87ee3-121">Property Statement</span><span class="sxs-lookup"><span data-stu-id="87ee3-121">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="87ee3-122">Get 문</span><span class="sxs-lookup"><span data-stu-id="87ee3-122">Get Statement</span></span>](../statements/get-statement.md)
