---
title: '방법: 디자인 타임에 새 설정 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: e371c60e3fb674e4243cec008e1098172725d4cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344964"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="4bfcb-102">방법: 디자인 타임에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="4bfcb-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="4bfcb-103">설정 디자이너를 사용 하 여 디자인 타임에 새 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="4bfcb-104">설정 디자이너에 새 설정 만들기 및 해당 설정에 대 한 속성을 지정할 수 있는 모눈 스타일 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="4bfcb-105">이름, 값, 형식 및 새로운 설정에 대 한 범위를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="4bfcb-106">설정의 만든 후 코드에서 액세스할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="4bfcb-107">C에서 디자인 타임에 새 설정을 만들려면\#</span><span class="sxs-lookup"><span data-stu-id="4bfcb-107">To create a new setting at design time in C\#</span></span>
  
1. <span data-ttu-id="4bfcb-108">**솔루션 탐색기**를 확장 합니다 **속성** 프로젝트의 노드.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2. <span data-ttu-id="4bfcb-109">새 설정을 추가 하려면 원하는.settings 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="4bfcb-110">이 파일에 대 한 기본 이름이 생성 되는 Settings.settings 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-110">The default name for this file is Settings.settings.</span></span>  
  
3. <span data-ttu-id="4bfcb-111">설정 디자이너에서 이름, 값, 형식 및 설정에 대 한 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="4bfcb-112">각 행에는 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="4bfcb-113">Visual Basic에서 디자인 타임에 새 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4bfcb-113">To create a new setting at design time in Visual Basic</span></span>  
  
1. <span data-ttu-id="4bfcb-114">**솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="4bfcb-115">**속성** 페이지에서 선택 합니다 **설정** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3. <span data-ttu-id="4bfcb-116">설정 디자이너에서 이름, 값, 형식 및 설정에 대 한 범위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="4bfcb-117">각 행에는 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bfcb-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfcb-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="4bfcb-118">See also</span></span>

- [<span data-ttu-id="4bfcb-119">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="4bfcb-119">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="4bfcb-120">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="4bfcb-120">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="4bfcb-121">방법: 디자인 타임에 기존 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="4bfcb-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
