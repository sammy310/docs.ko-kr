---
description: '자세히 알아보기: BC42017: 런타임에 바인딩 확인; 런타임 오류가 발생할 수 있습니다.'
title: 런타임에 바인딩을 확인합니다. 런타임 오류가 발생할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 2c783a7aff46df8ab033463f49c45f4c797220ea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795926"
---
# <a name="bc42017-late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="277e1-103">BC42017: 런타임에 바인딩 확인; 런타임 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-103">BC42017: Late bound resolution; runtime errors could occur</span></span>

<span data-ttu-id="277e1-104">개체는 [개체 데이터 형식](../data-types/object-data-type.md)으로 선언 된 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-104">An object is assigned to a variable declared to be of the [Object Data Type](../data-types/object-data-type.md).</span></span>

 <span data-ttu-id="277e1-105">변수를로 선언 하는 경우 `Object` 컴파일러는 런타임에 *바인딩을* 수행 해야 하므로 런타임에 추가 작업이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-105">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="277e1-106">또한 애플리케이션이 잠재적인 런타임 오류에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-106">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="277e1-107">예를 들어를 변수에 할당 한 <xref:System.Windows.Forms.Form> `Object` 다음 속성에 액세스 하려고 하면 <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> <xref:System.MemberAccessException> <xref:System.Windows.Forms.Form> 클래스가 속성을 노출 하지 않기 때문에 런타임이을 throw 합니다 `NameTable` .</span><span class="sxs-lookup"><span data-stu-id="277e1-107">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>

 <span data-ttu-id="277e1-108">변수를 특정 형식으로 선언 하는 경우 컴파일러는 컴파일 타임에 *초기 바인딩을* 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-108">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="277e1-109">이로 인해 성능이 향상 되 고, 특정 형식의 멤버에 대 한 액세스를 제어 하 고, 코드 가독성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-109">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>

 <span data-ttu-id="277e1-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-110">By default, this message is a warning.</span></span> <span data-ttu-id="277e1-111">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="277e1-111">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="277e1-112">**오류 ID:** BC42017</span><span class="sxs-lookup"><span data-stu-id="277e1-112">**Error ID:** BC42017</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="277e1-113">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="277e1-113">To correct this error</span></span>

- <span data-ttu-id="277e1-114">가능 하면 변수를 특정 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="277e1-114">If possible, declare the variable to be of a specific type.</span></span>

## <a name="see-also"></a><span data-ttu-id="277e1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="277e1-115">See also</span></span>

- [<span data-ttu-id="277e1-116">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="277e1-116">Early and Late Binding</span></span>](../../programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="277e1-117">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="277e1-117">Object Variable Declaration</span></span>](../../programming-guide/language-features/variables/object-variable-declaration.md)
