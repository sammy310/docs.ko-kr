---
title: 애플리케이션 설정 및 사용자 설정 사용
ms.date: 03/30/2017
description: 응용 프로그램 설정 및 사용자 설정을 사용 하 여 응용 프로그램 실행 세션 간에 유지 되는 값을 만들고 액세스 하는 방법에 대해 알아봅니다.
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
ms.openlocfilehash: a30fd354986265eca002fce57bccf5b3bb2adc15
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903170"
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="48efd-103">애플리케이션 설정 및 사용자 설정 사용</span><span class="sxs-lookup"><span data-stu-id="48efd-103">Using Application Settings and User Settings</span></span>
<span data-ttu-id="48efd-104">2.0 .NET Framework부터 응용 프로그램 실행 세션 간에 유지 되는 값을 만들고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-104">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="48efd-105">이러한 값을 *설정*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-105">These values are called *settings*.</span></span> <span data-ttu-id="48efd-106">설정은 사용자 기본 설정 또는 응용 프로그램에서 사용 해야 하는 중요 한 정보를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-106">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="48efd-107">예를 들어 응용 프로그램의 색 구성표에 대 한 사용자 기본 설정을 저장 하는 일련의 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-107">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="48efd-108">또는 응용 프로그램에서 사용 하는 데이터베이스를 지정 하는 연결 문자열을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-108">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="48efd-109">설정을 사용 하면 코드 외부의 응용 프로그램에 중요 한 정보를 유지 하 고 개별 사용자의 기본 설정을 저장 하는 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-109">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="48efd-110">이 단원의 항목에서는 디자인 타임 및 런타임에 설정을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-110">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48efd-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="48efd-111">In This Section</span></span>  
 [<span data-ttu-id="48efd-112">방법: 디자인 타임에 새 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="48efd-112">How To: Create a New Setting at Design Time</span></span>](how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="48efd-113">Visual Studio를 사용 하 여 응용 프로그램에 대 한 새 설정을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-113">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="48efd-114">방법: 디자인 타임에 기존 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="48efd-114">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="48efd-115">Visual Studio를 사용 하 여 기존 설정 값을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-115">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="48efd-116">방법: 애플리케이션 세션 간 설정 값 변경</span><span class="sxs-lookup"><span data-stu-id="48efd-116">How To: Change the Value of a Setting Between Application Sessions</span></span>](how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="48efd-117">응용 프로그램 세션 간에 컴파일된 응용 프로그램에서 설정 값을 변경 하는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-117">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="48efd-118">방법: C#을 사용하여 런타임에 설정 읽기</span><span class="sxs-lookup"><span data-stu-id="48efd-118">How To: Read Settings at Run Time With C#</span></span>](how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="48efd-119">C #을 사용 하 여 코드를 사용 하 여 설정을 읽는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-119">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="48efd-120">방법: C#을 사용하여 런타임에 사용자 설정 쓰기</span><span class="sxs-lookup"><span data-stu-id="48efd-120">How To: Write User Settings at Run Time with C#</span></span>](how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="48efd-121">C #을 사용 하 여 사용자 설정의 값을 작성 하 고 저장 하는 코드를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-121">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="48efd-122">방법: C#에서 애플리케이션에 여러 설정 집합 추가</span><span class="sxs-lookup"><span data-stu-id="48efd-122">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="48efd-123">C #을 사용 하 여 여러 설정 집합을 응용 프로그램에 추가 하는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="48efd-123">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48efd-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48efd-124">See also</span></span>

- [<span data-ttu-id="48efd-125">Windows Forms 애플리케이션 설정</span><span class="sxs-lookup"><span data-stu-id="48efd-125">Application Settings for Windows Forms</span></span>](application-settings-for-windows-forms.md)
