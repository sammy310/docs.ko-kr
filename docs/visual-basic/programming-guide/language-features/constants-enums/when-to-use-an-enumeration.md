---
title: 열거형을 사용하는 경우
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353954"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="e6b86-102">열거형을 사용하는 경우(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6b86-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="e6b86-103">Enumerations offer an easy way to work with sets of related constants.</span><span class="sxs-lookup"><span data-stu-id="e6b86-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="e6b86-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span><span class="sxs-lookup"><span data-stu-id="e6b86-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="e6b86-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span><span class="sxs-lookup"><span data-stu-id="e6b86-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="e6b86-106">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="e6b86-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="e6b86-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span><span class="sxs-lookup"><span data-stu-id="e6b86-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="e6b86-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span><span class="sxs-lookup"><span data-stu-id="e6b86-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="e6b86-109">The benefits of using enumerations include:</span><span class="sxs-lookup"><span data-stu-id="e6b86-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="e6b86-110">Reduces errors caused by transposing or mistyping numbers.</span><span class="sxs-lookup"><span data-stu-id="e6b86-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="e6b86-111">Makes it easy to change values in the future.</span><span class="sxs-lookup"><span data-stu-id="e6b86-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="e6b86-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span><span class="sxs-lookup"><span data-stu-id="e6b86-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="e6b86-113">Ensures forward compatibility.</span><span class="sxs-lookup"><span data-stu-id="e6b86-113">Ensures forward compatibility.</span></span> <span data-ttu-id="e6b86-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span><span class="sxs-lookup"><span data-stu-id="e6b86-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="e6b86-115">Naming Enumerations</span><span class="sxs-lookup"><span data-stu-id="e6b86-115">Naming Enumerations</span></span>  
 <span data-ttu-id="e6b86-116">Use a naming convention for enumeration members.</span><span class="sxs-lookup"><span data-stu-id="e6b86-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="e6b86-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span><span class="sxs-lookup"><span data-stu-id="e6b86-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="e6b86-118">Use a unique prefix that identifies the values from your application or component.</span><span class="sxs-lookup"><span data-stu-id="e6b86-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="e6b86-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span><span class="sxs-lookup"><span data-stu-id="e6b86-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="e6b86-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="e6b86-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="e6b86-121">Predefined Enumerations</span><span class="sxs-lookup"><span data-stu-id="e6b86-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="e6b86-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span><span class="sxs-lookup"><span data-stu-id="e6b86-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="e6b86-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="e6b86-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b86-124">참조</span><span class="sxs-lookup"><span data-stu-id="e6b86-124">See also</span></span>

- [<span data-ttu-id="e6b86-125">How to: Declare an Enumeration</span><span class="sxs-lookup"><span data-stu-id="e6b86-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="e6b86-126">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="e6b86-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="e6b86-127">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="e6b86-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="e6b86-128">How to: Iterate Through An Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6b86-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="e6b86-129">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="e6b86-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="e6b86-130">Enum 문</span><span class="sxs-lookup"><span data-stu-id="e6b86-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="e6b86-131">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="e6b86-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
