---
title: "'<interfacename>. <membername>'은 이미 구현 된 기본 클래스에 의해'<baseclassname>'. 다시 구현 <type> 가정"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 5943eff5fa7e68da9905e3e589eea264c06943c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593312"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="da545-103">'\<interfacename >. \<membername >'는 기본 클래스 의해 이미 구현\<baseclassname >'입니다.</span><span class="sxs-lookup"><span data-stu-id="da545-103">'\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="da545-104">다시 구현 \<유형 > 가정</span><span class="sxs-lookup"><span data-stu-id="da545-104">Re-implementation of \<type> assumed</span></span>
<span data-ttu-id="da545-105">속성, 프로시저 또는 파생된 클래스에서 이벤트를 사용 하는 `Implements` 절을 이미 기본 클래스에서 구현 된 인터페이스 멤버를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da545-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="da545-106">파생 클래스는 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da545-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="da545-107">이는 기본 클래스 구현 재정의와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="da545-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="da545-108">자세한 내용은 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da545-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="da545-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="da545-109">By default, this message is a warning.</span></span> <span data-ttu-id="da545-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="da545-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="da545-111">**오류 ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="da545-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da545-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="da545-112">To correct this error</span></span>  
  
- <span data-ttu-id="da545-113">인터페이스 멤버를 다시 구현하려는 경우 어떤 조치도 취할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da545-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="da545-114">사용 하지 않는 경우 파생된 클래스의 코드가 다시 구현 된 멤버에 액세스 합니다 `MyBase` 키워드를 기본 클래스 구현에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="da545-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
- <span data-ttu-id="da545-115">인터페이스 멤버를 다시 구현하지 않으려는 경우 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="da545-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da545-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="da545-116">See also</span></span>

- [<span data-ttu-id="da545-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="da545-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
