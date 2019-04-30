---
title: My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: ca31e1c40c77bf7f42d246019d81f4ffaed646e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62014455"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="f531a-102">My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f531a-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="f531a-103">합니다 [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) 하 고 [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) 개체 폼, 데이터 원본 및 응용 프로그램에서 사용 하는 XML Web services에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="f531a-104">컬렉션을 제공 하 여 이렇게 *인스턴스를 기본* 이러한 각 개체의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="f531a-105">기본 인스턴스</span><span class="sxs-lookup"><span data-stu-id="f531a-105">Default Instances</span></span>  
 <span data-ttu-id="f531a-106">기본 인스턴스가 될 필요가 없습니다 런타임에서 제공 하는 클래스의 인스턴스를 선언 하 고 사용 하 여 인스턴스화할 합니다 `Dim` 및 `New` 문.</span><span class="sxs-lookup"><span data-stu-id="f531a-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="f531a-107">다음 예제에서는 어떻게 하면 선언 하 고 인스턴스를 인스턴스화할를 <xref:System.Windows.Forms.Form> 라는 클래스 `Form1`, 어떻게 되 고 이제 수의 기본 인스턴스를 가져오는 <xref:System.Windows.Forms.Form> 클래스를 통해 `My.Forms`합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="f531a-108">합니다 `My.Forms` 개체에 대 한 기본 인스턴스의 컬렉션을 반환 합니다. 모든 `Form` 프로젝트에 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="f531a-109">마찬가지로, `My.WebServices` 만들었다고에 대 한 참조 응용 프로그램에서 모든 웹 서비스에 대 한 프록시 클래스의 기본 인스턴스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f531a-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f531a-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="f531a-110">See also</span></span>

- [<span data-ttu-id="f531a-111">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="f531a-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="f531a-112">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="f531a-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="f531a-113">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="f531a-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
