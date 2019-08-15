---
title: '방법: 디자인 타임에 새 설정 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037900"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="7d52a-102">방법: 디자인 타임에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="7d52a-102">How To: Create a new setting at design time</span></span>

<span data-ttu-id="7d52a-103">디자인 타임에 Visual Studio의 설정 디자이너를 사용 하 여 새 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-103">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="7d52a-104">설정 디자이너는 새 설정을 만들고 이러한 설정에 대 한 속성을 지정할 수 있는 그리드 스타일 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="7d52a-105">새 설정의 이름, 값, 유형 및 범위를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="7d52a-106">설정이 만들어지면 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-106">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="7d52a-107">C에서 디자인 타임에 새 설정 만들기\#</span><span class="sxs-lookup"><span data-stu-id="7d52a-107">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="7d52a-108">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-108">Open Visual Studio.</span></span>

2. <span data-ttu-id="7d52a-109">**솔루션 탐색기**에서 프로젝트의 **속성** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-109">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="7d52a-110">새 설정을 추가할 settings 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-110">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="7d52a-111">이 파일의 기본 이름은 Settings입니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-111">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="7d52a-112">설정 디자이너에서 설정의 **이름**, **값**, **유형**및 **범위** 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-112">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="7d52a-113">각 행은 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-113">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="7d52a-114">디자인 타임에 Visual Basic에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="7d52a-114">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="7d52a-115">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="7d52a-116">**솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-116">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="7d52a-117">**속성** 페이지에서 **설정** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-117">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="7d52a-118">설정 디자이너에서 설정의 **이름**, **값**, **유형**및 **범위** 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-118">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="7d52a-119">각 행은 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d52a-119">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d52a-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="7d52a-120">See also</span></span>

- [<span data-ttu-id="7d52a-121">응용 프로그램 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="7d52a-121">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="7d52a-122">응용 프로그램 설정 개요</span><span class="sxs-lookup"><span data-stu-id="7d52a-122">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="7d52a-123">방법: 디자인 타임에 기존 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="7d52a-123">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
