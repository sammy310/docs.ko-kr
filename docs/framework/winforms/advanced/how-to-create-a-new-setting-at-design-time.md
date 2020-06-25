---
title: '방법: 디자인 타임에 새 설정 만들기'
description: Visual Studio의 설정 디자이너를 사용 하 여 디자인 타임에 새 Windows Forms 설정을 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325846"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="47be3-103">방법: 디자인 타임에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="47be3-103">How To: Create a new setting at design time</span></span>

<span data-ttu-id="47be3-104">디자인 타임에 Visual Studio의 설정 디자이너를 사용 하 여 새 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-104">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="47be3-105">설정 디자이너는 새 설정을 만들고 이러한 설정에 대 한 속성을 지정할 수 있는 그리드 스타일 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-105">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="47be3-106">새 설정의 이름, 값, 유형 및 범위를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-106">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="47be3-107">설정이 만들어지면 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-107">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="47be3-108">C에서 디자인 타임에 새 설정 만들기\#</span><span class="sxs-lookup"><span data-stu-id="47be3-108">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="47be3-109">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-109">Open Visual Studio.</span></span>

2. <span data-ttu-id="47be3-110">**솔루션 탐색기**에서 프로젝트의 **속성** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-110">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="47be3-111">새 설정을 추가할 settings 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-111">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="47be3-112">이 파일의 기본 이름은 Settings입니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-112">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="47be3-113">설정 디자이너에서 설정의 **이름**, **값**, **유형**및 **범위** 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-113">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="47be3-114">각 행은 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-114">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="47be3-115">디자인 타임에 Visual Basic에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="47be3-115">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="47be3-116">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-116">Open Visual Studio.</span></span>

2. <span data-ttu-id="47be3-117">**솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-117">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="47be3-118">**속성** 페이지에서 **설정** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-118">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="47be3-119">설정 디자이너에서 설정의 **이름**, **값**, **유형**및 **범위** 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-119">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="47be3-120">각 행은 단일 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="47be3-120">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="47be3-121">참조</span><span class="sxs-lookup"><span data-stu-id="47be3-121">See also</span></span>

- [<span data-ttu-id="47be3-122">애플리케이션 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="47be3-122">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="47be3-123">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="47be3-123">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="47be3-124">방법: 디자인 타임에 기존 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="47be3-124">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
