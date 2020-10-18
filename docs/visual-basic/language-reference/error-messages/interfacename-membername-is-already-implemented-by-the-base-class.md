---
title: "'<interfacename>.<membername>'은 기본 클래스 '<baseclassname>'에 의해 이미 구현되어 있습니다. <type>을 다시 구현하는 것으로 간주합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 8137f6b1712b6a0752a991f5a3d598b5f958252c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162819"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a><span data-ttu-id="3ddd4-103">BC42015: ' \<interfacename> . \<membername> '은 (는) 기본 클래스 ' '에 의해 이미 구현 되었습니다 \<baseclassname> .</span><span class="sxs-lookup"><span data-stu-id="3ddd4-103">BC42015: '\<interfacename>.\<membername>' is already implemented by the base class '\<baseclassname>'.</span></span> <span data-ttu-id="3ddd4-104">\<type>을 다시 구현하는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-104">Re-implementation of \<type> assumed</span></span>

<span data-ttu-id="3ddd4-105">파생 클래스의 속성, 프로시저 또는 이벤트는 `Implements` 기본 클래스에서 이미 구현 된 인터페이스 멤버를 지정 하는 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>

 <span data-ttu-id="3ddd4-106">파생 클래스는 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="3ddd4-107">이는 기본 클래스 구현 재정의와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="3ddd4-108">자세한 내용은 [Implements](../statements/implements-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-108">For more information, see [Implements](../statements/implements-clause.md).</span></span>

 <span data-ttu-id="3ddd4-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-109">By default, this message is a warning.</span></span> <span data-ttu-id="3ddd4-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="3ddd4-111">**오류 ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="3ddd4-111">**Error ID:** BC42015</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="3ddd4-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3ddd4-112">To correct this error</span></span>

- <span data-ttu-id="3ddd4-113">인터페이스 멤버를 다시 구현하려는 경우 어떤 조치도 취할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="3ddd4-114">키워드를 사용 하 여 기본 클래스 구현에 액세스 하지 않는 경우 파생 클래스의 코드가 다시 구현 멤버에 액세스 합니다 `MyBase` .</span><span class="sxs-lookup"><span data-stu-id="3ddd4-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>

- <span data-ttu-id="3ddd4-115">인터페이스 멤버를 다시 구현하지 않으려는 경우 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3ddd4-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ddd4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ddd4-116">See also</span></span>

- [<span data-ttu-id="3ddd4-117">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3ddd4-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
