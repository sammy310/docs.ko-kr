---
description: '자세한 정보: 방법: Visual Basic에서 사용자 설정 유지'
title: '방법: 사용자 설정 유지'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], persisting user settings
- persistence [Visual Basic], persisting user settings [Visual Basic]
- user settings [Visual Basic], persisting
ms.assetid: 0e5e6415-b6e2-4602-9be0-a65fa167d007
ms.openlocfilehash: 43ca82442678356afacb8e05149a35d485603059
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797837"
---
# <a name="how-to-persist-user-settings-in-visual-basic"></a><span data-ttu-id="8fc98-103">방법: Visual Basic에서 사용자 설정 유지</span><span class="sxs-lookup"><span data-stu-id="8fc98-103">How to: Persist User Settings in Visual Basic</span></span>

<span data-ttu-id="8fc98-104">`My.Settings.Save` 메서드를 사용하여 사용자 설정에 대한 변경 내용을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-104">You can use the `My.Settings.Save` method to persist changes to the user settings.</span></span>  
  
 <span data-ttu-id="8fc98-105">일반적으로 애플리케이션은 해당 애플리케이션이 종료될 때 사용자 설정에 대한 변경 내용을 유지하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-105">Typically, applications are designed to persist the changes to the user settings when the application shuts down.</span></span> <span data-ttu-id="8fc98-106">이는 여러 가지 요인에 따라 몇 초마다 설정이 저장될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-106">This is because saving the settings can take, depending on several factors, several seconds.</span></span>  
  
 <span data-ttu-id="8fc98-107">자세한 내용은 [My.Settings 개체](../../../language-reference/objects/my-settings-object.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fc98-107">For more information, see [My.Settings Object](../../../language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8fc98-108">런타임에 사용자 범위의 값을 변경하고 저장할 수 있지만 애플리케이션 범위 설정은 읽기 전용이고 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="8fc98-109">**프로젝트 디자이너** 를 통해 또는 애플리케이션의 구성 파일을 편집하여 애플리케이션을 만들 때 애플리케이션 범위 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-109">You can change application-scope settings when creating the application, through the **Project Designer**, or by editing the application's configuration file.</span></span> <span data-ttu-id="8fc98-110">자세한 내용은 [애플리케이션 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fc98-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fc98-111">예제</span><span class="sxs-lookup"><span data-stu-id="8fc98-111">Example</span></span>  

 <span data-ttu-id="8fc98-112">이 예제에서는 `LastChanged` 사용자 설정의 값을 변경하고 `My.Settings.Save` 메서드를 호출하여 해당 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-112">This example changes the value of the `LastChanged` user setting and saves that change by calling the `My.Settings.Save` method.</span></span>  
  
 [!code-vb[VbVbalrMyResources#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#5)]  
  
 <span data-ttu-id="8fc98-113">이 예제가 작동하려면 애플리케이션에 `Date` 형식의 `LastChanged` 사용자 설정이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fc98-113">For this example to work, your application must have a `LastChanged` user setting, of type `Date`.</span></span> <span data-ttu-id="8fc98-114">자세한 내용은 [애플리케이션 설정 관리(.NET)](/visualstudio/ide/managing-application-settings-dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fc98-114">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc98-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fc98-115">See also</span></span>

- [<span data-ttu-id="8fc98-116">My.Settings 개체</span><span class="sxs-lookup"><span data-stu-id="8fc98-116">My.Settings Object</span></span>](../../../language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="8fc98-117">방법: Visual Basic에서 애플리케이션 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="8fc98-117">How to: Read Application Settings in Visual Basic</span></span>](how-to-read-application-settings.md)
- [<span data-ttu-id="8fc98-118">방법: Visual Basic에서 사용자 설정 변경</span><span class="sxs-lookup"><span data-stu-id="8fc98-118">How to: Change User Settings in Visual Basic</span></span>](how-to-change-user-settings.md)
- [<span data-ttu-id="8fc98-119">방법: Visual Basic에서 사용자 설정의 속성 표 만들기</span><span class="sxs-lookup"><span data-stu-id="8fc98-119">How to: Create Property Grids for User Settings in Visual Basic</span></span>](how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="8fc98-120">애플리케이션 설정 관리(.NET)</span><span class="sxs-lookup"><span data-stu-id="8fc98-120">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
