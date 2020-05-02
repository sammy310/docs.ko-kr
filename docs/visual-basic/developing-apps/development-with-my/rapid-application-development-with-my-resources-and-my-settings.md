---
title: My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349260"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="df58f-102">My.Resources 및 My.Settings를 사용한 신속한 애플리케이션 개발(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df58f-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>

<span data-ttu-id="df58f-103">`My.Resources` 개체는 애플리케이션의 리소스에 대한 액세스를 제공하고 애플리케이션의 리소스를 동적으로 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="df58f-104">리소스 검색</span><span class="sxs-lookup"><span data-stu-id="df58f-104">Retrieving Resources</span></span>  

 <span data-ttu-id="df58f-105">`My.Resources` 개체를 통해 오디오 파일, 아이콘, 이미지 및 문자열과 같은 여러 리소스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="df58f-106">예를 들어 애플리케이션의 문화권별 리소스 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="df58f-107">다음 예제에서는 양식의 아이콘을 애플리케이션의 리소스 파일에 저장된 `Form1Icon`이라는 아이콘으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 <span data-ttu-id="df58f-108">`My.Resources` 개체는 글로벌 리소스만 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="df58f-109">양식과 관련된 리소스 파일에 대한 액세스 권한은 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="df58f-110">양식에서 양식 리소스에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="df58f-111">마찬가지로 `My.Settings` 개체는 애플리케이션 설정에 대한 액세스를 제공하며 애플리케이션에 대한 속성 설정과 기타 정보를 동적으로 저장하고 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="df58f-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="df58f-112">자세한 내용은 [My.Resources 개체](../../../visual-basic/language-reference/objects/my-resources-object.md) 및 [My.Settings 개체](../../../visual-basic/language-reference/objects/my-settings-object.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df58f-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df58f-113">참조</span><span class="sxs-lookup"><span data-stu-id="df58f-113">See also</span></span>

- [<span data-ttu-id="df58f-114">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="df58f-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [<span data-ttu-id="df58f-115">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="df58f-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="df58f-116">애플리케이션 설정 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df58f-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
