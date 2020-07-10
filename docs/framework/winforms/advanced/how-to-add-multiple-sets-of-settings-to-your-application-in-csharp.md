---
title: '방법: C#에서 애플리케이션에 여러 설정 집합 추가'
description: 'Visual Studio를 사용 하 여 c #에서 응용 프로그램에 여러 Windows Forms 설정 집합을 추가 하는 방법에 대해 알아봅니다.'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 579374ff101758b3224bc122c46b891280ed2609
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173447"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a><span data-ttu-id="05f71-103">방법: C에서 응용 프로그램에 여러 설정 집합 추가\#</span><span class="sxs-lookup"><span data-stu-id="05f71-103">How To: Add Multiple Sets of Settings To Your Application in C\#</span></span>

<span data-ttu-id="05f71-104">응용 프로그램에서 여러 설정 집합을 사용할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-104">In some cases, you might want to have multiple sets of settings in an application.</span></span> <span data-ttu-id="05f71-105">예를 들어 특정 설정 그룹이 자주 변경 될 것으로 예상 되는 응용 프로그램을 개발 하는 경우 해당 파일을 단일 파일로 분리 하 여 다른 설정을 영향을 받지 않는 상태로 유지 하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-105">For example, if you are developing an application where a particular group of settings is expected to change frequently, it might be wise to separate them all into a single file so that the file can be replaced wholesale, leaving other settings unaffected.</span></span> <span data-ttu-id="05f71-106">Visual Studio에서는 여러 설정 집합을 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-106">Visual Studio allows you to add multiple sets of settings to your project.</span></span> <span data-ttu-id="05f71-107">개체를 통해 추가 설정 집합에 액세스할 수 있습니다 `Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="05f71-107">Additional sets of settings can be accessed via the `Properties.Settings` object.</span></span>

## <a name="add-an-additional-set-of-settings"></a><span data-ttu-id="05f71-108">추가 설정 집합 추가</span><span class="sxs-lookup"><span data-stu-id="05f71-108">Add an Additional Set of Settings</span></span>

1. <span data-ttu-id="05f71-109">Visual Studio의 **프로젝트** 메뉴에서 **새 항목 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-109">In Visual Studio, from the **Project** menu, choose **Add New Item**.</span></span>

   <span data-ttu-id="05f71-110">**새 항목 추가** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-110">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="05f71-111">**새 항목 추가** 대화 상자에서 **설정 파일**을 선택 하 고 파일 이름을 입력 한 다음 **추가** 를 클릭 하 여 새 설정 파일을 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-111">In the **Add New Item** dialog box, select **Settings File**, enter a name for the file, and click **Add** to add a new settings file to your solution.</span></span>

3. <span data-ttu-id="05f71-112">**솔루션 탐색기**에서 새 설정 파일을 **속성** 폴더로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-112">In **Solution Explorer**, drag the new Settings file into the **Properties** folder.</span></span> <span data-ttu-id="05f71-113">이렇게 하면 코드에서 새 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-113">This allows your new settings to be available in code.</span></span>

4. <span data-ttu-id="05f71-114">다른 설정 파일과 마찬가지로이 파일에서 설정을 추가 하 고 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05f71-114">Add and use settings in this file as you would any other settings file.</span></span> <span data-ttu-id="05f71-115">개체를 통해이 설정 그룹에 액세스할 수 있습니다 `Properties.Settings` .</span><span class="sxs-lookup"><span data-stu-id="05f71-115">You can access this group of settings via the `Properties.Settings` object.</span></span>

## <a name="see-also"></a><span data-ttu-id="05f71-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05f71-116">See also</span></span>

- [<span data-ttu-id="05f71-117">애플리케이션 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="05f71-117">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="05f71-118">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="05f71-118">Application Settings Overview</span></span>](application-settings-overview.md)
