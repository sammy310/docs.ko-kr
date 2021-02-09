---
description: '자세한 정보: My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)'
title: My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 34363a56577ca0fafb839e782a8066bd8a8c5a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775359"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="3bf0f-103">My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3bf0f-103">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="3bf0f-104">[My.Forms](../../language-reference/objects/my-forms-object.md) 및 [My.WebServices](../../language-reference/objects/my-webservices-object.md) 개체는 애플리케이션에서 사용되는 폼, 데이터 원본 및 XML Web services에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf0f-104">The [My.Forms](../../language-reference/objects/my-forms-object.md) and [My.WebServices](../../language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="3bf0f-105">이들 각 개체의 ‘기본 인스턴스’ 컬렉션을 통해 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf0f-105">They provide access through collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="3bf0f-106">기본 인스턴스</span><span class="sxs-lookup"><span data-stu-id="3bf0f-106">Default Instances</span></span>  

 <span data-ttu-id="3bf0f-107">기본 인스턴스는 런타임이 제공하는 클래스의 인스턴스이고 `Dim` 및 `New` 문을 사용하여 선언하고 인스턴스화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf0f-107">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="3bf0f-108">다음 예제에서는 `Form1`이라는 <xref:System.Windows.Forms.Form> 클래스의 인스턴스를 선언하고 인스턴스화한 후 `My.Forms`를 통해 이 <xref:System.Windows.Forms.Form> 클래스의 기본 인스턴스를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bf0f-108">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="3bf0f-109">`My.Forms` 개체는 프로젝트에 있는 모든 `Form` 클래스의 기본 인스턴스 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf0f-109">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="3bf0f-110">마찬가지로 `My.WebServices`는 애플리케이션에서 참조를 만든 모든 웹 서비스에 대한 프록시 클래스의 기본 인스턴스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bf0f-110">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf0f-111">참조</span><span class="sxs-lookup"><span data-stu-id="3bf0f-111">See also</span></span>

- [<span data-ttu-id="3bf0f-112">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="3bf0f-112">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="3bf0f-113">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="3bf0f-113">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="3bf0f-114">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="3bf0f-114">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
