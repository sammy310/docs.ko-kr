---
title: C#에서 상수 정의 방법
description: 컴파일 시간에 값이 설정되는 필드인 C#에서 상수를 정의하는 방법에 대해 알아봅니다. 상수를 사용하여 특수 값에 의미 있는 이름을 제공합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: afa2799cf76f976e332f91b631dc90e2799a0aa0
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864646"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="aa1c2-104">C\#에서 상수 정의 방법</span><span class="sxs-lookup"><span data-stu-id="aa1c2-104">How to define constants in C\#</span></span>
<span data-ttu-id="aa1c2-105">상수는 해당 값이 컴파일 시간에 설정되며 변경할 수 없는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-105">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="aa1c2-106">상수를 사용하여 특수 값에 대해 숫자 리터럴(“매직 넘버”) 대신 의미 있는 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-106">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa1c2-107">C#에서는 [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) 전처리기 지시문을 사용하여 일반적으로 C와 C++에서 사용되는 방식으로 상수를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-107">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="aa1c2-108">정수 형식(`int`, `byte` 등)의 상수 값을 정의하려면 열거 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-108">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="aa1c2-109">자세한 내용은 [enum](../../language-reference/builtin-types/enum.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-109">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="aa1c2-110">정수가 아닌 상수를 정의하는 한 가지 방법은 `Constants`라는 단일 정적 클래스로 그룹화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-110">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="aa1c2-111">이 경우 다음 예제와 같이 상수에 대한 모든 참조 앞에 클래스 이름이 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-111">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa1c2-112">예제</span><span class="sxs-lookup"><span data-stu-id="aa1c2-112">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="aa1c2-113">클래스 이름 한정자를 통해 사용자와 상수를 사용하는 다른 사용자가 상수이며 수정할 수 없음을 쉽게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa1c2-113">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1c2-114">참조</span><span class="sxs-lookup"><span data-stu-id="aa1c2-114">See also</span></span>

- [<span data-ttu-id="aa1c2-115">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="aa1c2-115">Classes and Structs</span></span>](./index.md)
