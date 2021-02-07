---
description: '자세한 정보: BC32098: 형식 매개 변수는 한정자로 사용할 수 없습니다.'
title: 형식 매개 변수는 한정자로 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 61be8e81c9cf6c7a8339c7bbf0ad9566f582eb57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675054"
---
# <a name="bc32098-type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="412fd-103">BC32098: 형식 매개 변수는 한정자로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-103">BC32098: Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="412fd-104">프로그래밍 요소는 형식 매개 변수를 포함 하는 한정 문자열을 사용 하 여 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-104">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="412fd-105">형식 매개 변수는 제네릭 형식이 생성 될 때 제공 되는 형식에 대 한 요구 사항을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-105">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="412fd-106">특정 정의 된 형식을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-106">It does not represent a specific defined type.</span></span> <span data-ttu-id="412fd-107">정규화 문자열에는 컴파일 시간에 정의 된 요소만 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-107">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="412fd-108">다음 코드는이 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-108">The following code can generate this error:</span></span>

```vb
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean

    Dim saveText As c.Text
    ' Insert code to look for badText within saveText.
End Function
```

 <span data-ttu-id="412fd-109">**오류 ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="412fd-109">**Error ID:** BC32098</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="412fd-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="412fd-110">To correct this error</span></span>

1. <span data-ttu-id="412fd-111">정규화 문자열에서 형식 매개 변수를 제거 하거나 정의 된 형식으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-111">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>

2. <span data-ttu-id="412fd-112">정규화 된 프로그래밍 요소를 찾기 위해 생성 된 형식을 사용 해야 하는 경우에는 추가 프로그램 논리를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="412fd-112">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>

## <a name="see-also"></a><span data-ttu-id="412fd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="412fd-113">See also</span></span>

- [<span data-ttu-id="412fd-114">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="412fd-114">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="412fd-115">Visual Basic의 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="412fd-115">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="412fd-116">Type List</span><span class="sxs-lookup"><span data-stu-id="412fd-116">Type List</span></span>](../statements/type-list.md)
