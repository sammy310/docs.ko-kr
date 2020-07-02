---
title: 시작 화면을 추가 하는 방법
description: 시작 창 또는 시작 화면을 Windows Presentation Foundation (WPF) 응용 프로그램에 추가 하는 방법을 알아봅니다.
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 0d0cf2e2a550320650c3b4a0c257071a0403c32b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617962"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="7156a-103">방법: WPF 애플리케이션에 시작 화면 추가</span><span class="sxs-lookup"><span data-stu-id="7156a-103">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="7156a-104">이 항목에서는 시작 창 또는 *시작 화면*을 WINDOWS PRESENTATION FOUNDATION (WPF) 응용 프로그램에 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-104">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="7156a-105">기존 이미지를 시작 화면으로 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="7156a-105">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="7156a-106">시작 화면에 사용할 이미지를 만들거나 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-106">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="7156a-107">WIC (Windows Imaging Component)에서 지 원하는 모든 이미지 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-107">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="7156a-108">예를 들어 BMP, GIF, JPEG, PNG 또는 TIFF 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-108">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="7156a-109">WPF 응용 프로그램 프로젝트에 이미지 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-109">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="7156a-110">**솔루션 탐색기**에서 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-110">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="7156a-111">속성 창에서 **빌드 작업** 속성의 드롭다운 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="7156a-112">드롭다운 목록에서 **SplashScreen** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-112">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="7156a-113">**F5** 키를 눌러 응용 프로그램을 빌드하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-113">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="7156a-114">시작 화면 이미지가 화면 가운데에 표시 되 고 주 응용 프로그램 창이 표시 되 면 페이드 인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-114">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="7156a-115">빌드에서 시작 화면을 제외 하려면</span><span class="sxs-lookup"><span data-stu-id="7156a-115">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="7156a-116">**솔루션 탐색기**에서 시작 화면 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-116">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="7156a-117">**속성** 창에서 **빌드 작업** 을 **없음**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-117">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="7156a-118">응용 프로그램에서 시작 화면을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="7156a-118">To remove the splash screen from an application</span></span>

<span data-ttu-id="7156a-119">**솔루션 탐색기**에서 시작 화면 이미지를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7156a-119">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="7156a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7156a-120">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="7156a-121">[방법: 프로젝트에 기존 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7156a-121">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
