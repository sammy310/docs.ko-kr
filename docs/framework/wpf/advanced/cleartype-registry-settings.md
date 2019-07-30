---
title: ClearType 레지스트리 설정
ms.date: 03/30/2017
helpviewer_keywords:
- ClearType [WPF], registry settings
- typography [WPF], ClearType registry settings
ms.assetid: 56f314bb-b30b-4f67-8492-8b8a9fa432ae
ms.openlocfilehash: 8f1c4415a834f7eb7c3048a89ab81de6921b7bf6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629932"
---
# <a name="cleartype-registry-settings"></a><span data-ttu-id="6f3d1-102">ClearType 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-102">ClearType Registry Settings</span></span>
<span data-ttu-id="6f3d1-103">이 항목에서는 WPF 응용 프로그램에서 사용 되는 Microsoft ClearType 레지스트리 설정에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-103">This topic provides an overview of the Microsoft ClearType registry settings that are used by WPF applications.</span></span>  

<a name="overview"></a>   
## <a name="technology-overview"></a><span data-ttu-id="6f3d1-104">기술 개요</span><span class="sxs-lookup"><span data-stu-id="6f3d1-104">Technology Overview</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="6f3d1-105">디스플레이 장치에 텍스트를 렌더링 하는 응용 프로그램은 ClearType 기능을 사용 하 여 향상 된 읽기 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-105">applications that render text to a display device use ClearType features to provide an enhanced reading experience.</span></span> <span data-ttu-id="6f3d1-106">ClearType은에서 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 개발한 소프트웨어 기술로 랩톱 화면, Pocket PC 화면, 평면 패널 모니터 등 기존 lcd (액체 크리스탈 디스플레이)의 텍스트 가독성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-106">ClearType is a software technology developed by [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] that improves the readability of text on existing LCDs (Liquid Crystal Displays), such as laptop screens, Pocket PC screens and flat panel monitors.</span></span> <span data-ttu-id="6f3d1-107">ClearType은 LCD 화면의 모든 픽셀에서 개별 세로 색 줄무늬 요소에 액세스 하는 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-107">ClearType works by accessing the individual vertical color stripe elements in every pixel of an LCD screen.</span></span> <span data-ttu-id="6f3d1-108">ClearType에 대 한 자세한 내용은 [Cleartype 개요](cleartype-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-108">For more information on ClearType, see [ClearType Overview](cleartype-overview.md).</span></span>  
  
 <span data-ttu-id="6f3d1-109">ClearType으로 렌더링 되는 텍스트는 다양 한 디스플레이 장치에서 볼 때 현저 하 게 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-109">Text that is rendered with ClearType can appear significantly different when viewed on various display devices.</span></span> <span data-ttu-id="6f3d1-110">예를 들어 적은 수의 모니터가 색 스트라이프 요소를 보다 일반적인 빨강, 녹색, 파랑 ( [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) 순서 보다는 파란색, 녹색, 빨간색 순서로 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-110">For example, a small number of monitors implement the color stripe elements in blue, green, red order rather than the more common red, green, blue (    [!INCLUDE[TLA#tla_rgb](../../../../includes/tlasharptla-rgb-md.md)]) order.</span></span>  
  
 <span data-ttu-id="6f3d1-111">ClearType으로 렌더링 되는 텍스트는 다양 한 수준의 색 민감도를 사용 하 여 개인이 볼 때 크게 다르게 보일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-111">Text that is rendered with ClearType can also appear significantly different when viewed by individuals with varying levels of color sensitivity.</span></span> <span data-ttu-id="6f3d1-112">어떤 사람은 다른 사람보다 미묘한 색의 차이를 더 잘 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-112">Some individuals can detect slight differences in color better than others.</span></span>  
  
 <span data-ttu-id="6f3d1-113">이러한 각 경우에는 각 개인에 게 최상의 읽기 환경을 제공 하기 위해 ClearType 기능을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-113">In each of these cases, ClearType features need to be modified in order to provide the best reading experience for each individual.</span></span>  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a><span data-ttu-id="6f3d1-114">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="6f3d1-115">ClearType 기능을 제어 하기 위한 네 가지 레지스트리 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-115">specifies four registry settings for controlling ClearType features:</span></span>  
  
|<span data-ttu-id="6f3d1-116">설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-116">Setting</span></span>|<span data-ttu-id="6f3d1-117">Description</span><span class="sxs-lookup"><span data-stu-id="6f3d1-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f3d1-118">ClearType 수준</span><span class="sxs-lookup"><span data-stu-id="6f3d1-118">ClearType level</span></span>|<span data-ttu-id="6f3d1-119">ClearType 색의 명확성 수준을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-119">Describes the level of ClearType color clarity.</span></span>|  
|<span data-ttu-id="6f3d1-120">감마 수준</span><span class="sxs-lookup"><span data-stu-id="6f3d1-120">Gamma level</span></span>|<span data-ttu-id="6f3d1-121">디스플레이 디바이스의 픽셀 색 구성 요소 수준을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-121">Describes the level of the pixel color component for a display device.</span></span>|  
|<span data-ttu-id="6f3d1-122">픽셀 구조체</span><span class="sxs-lookup"><span data-stu-id="6f3d1-122">Pixel structure</span></span>|<span data-ttu-id="6f3d1-123">디스플레이 디바이스의 픽셀 배치를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-123">Describes the arrangement of pixels for a display device.</span></span>|  
|<span data-ttu-id="6f3d1-124">텍스트 대비 수준</span><span class="sxs-lookup"><span data-stu-id="6f3d1-124">Text contrast level</span></span>|<span data-ttu-id="6f3d1-125">표시되는 텍스트의 대비 수준을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-125">Describes the level of contrast for displayed text.</span></span>|  
  
 <span data-ttu-id="6f3d1-126">이러한 설정은 식별 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]된 ClearType 레지스트리 설정을 참조 하는 방법을 알고 있는 외부 구성 유틸리티에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-126">These settings can be accessed by an external configuration utility that knows how to reference the identified [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType registry settings.</span></span> <span data-ttu-id="6f3d1-127">이러한 설정은 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 레지스트리 편집기를 통해 직접 값에 액세스하여 만들거나 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-127">These settings can also be created or modified by accessing the values directly by using the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Registry Editor.</span></span>  
  
 <span data-ttu-id="6f3d1-128">ClearType 레지스트리 설정 (기본 상태)이 설정 되지 않은 경우 응용 프로그램은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 글꼴 다듬기 설정에 대 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 한 시스템 매개 변수 정보를 쿼리 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f3d1-128">If the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ClearType registry settings are not set (which is the default state), the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application queries the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] system parameters information for font smoothing settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f3d1-129">표시 장치 이름을 열거 하는 `SystemParametersInfo` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 방법에 대 한 자세한 내용은 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-129">For information on enumerating display device names, see the `SystemParametersInfo`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function.</span></span>  
  
<a name="ClearType_level"></a>   
## <a name="cleartype-level"></a><span data-ttu-id="6f3d1-130">ClearType 수준</span><span class="sxs-lookup"><span data-stu-id="6f3d1-130">ClearType Level</span></span>  
 <span data-ttu-id="6f3d1-131">ClearType 수준을 사용 하면 개인의 색 민감도 및 인식에 따라 텍스트 렌더링을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-131">The ClearType level allows you to adjust the rendering of text based on the color sensitivity and perception of an individual.</span></span> <span data-ttu-id="6f3d1-132">일부 개인의 경우 가장 높은 수준에서 ClearType을 사용 하는 텍스트를 렌더링 하는 것은 최상의 읽기 환경을 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-132">For some individuals, the rendering of text that uses ClearType at its highest level does not produce the best reading experience.</span></span>  
  
 <span data-ttu-id="6f3d1-133">ClearType 수준은 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-133">The ClearType level is an integer value that ranges from 0 to 100.</span></span> <span data-ttu-id="6f3d1-134">기본 수준은 100입니다. 즉, ClearType은 표시 장치에서 색 stripe 요소의 최대 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-134">The default level is 100, which means ClearType uses the maximum capability of the color stripe elements of the display device.</span></span> <span data-ttu-id="6f3d1-135">그러나 ClearType 수준 0은 텍스트를 회색 눈금으로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-135">However, a ClearType level of 0 renders text as gray scale.</span></span> <span data-ttu-id="6f3d1-136">ClearType 수준을 0에서 100 사이로 설정 하면 개인의 색 민감도에 적합 한 중간 수준을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-136">By setting the ClearType level somewhere between 0 and 100, you can create an intermediate level that is suitable to an individual's color sensitivity.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="6f3d1-137">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-137">Registry Setting</span></span>  
 <span data-ttu-id="6f3d1-138">ClearType 수준에 대 한 레지스트리 설정 위치는 특정 디스플레이 장치 이름에 해당 하는 개별 사용자 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-138">The registry setting location for the ClearType level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="6f3d1-139">사용자의 각 표시 장치 이름에 대해 `ClearTypeLevel` DWORD 값이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-139">For each display device name for a user, a `ClearTypeLevel` DWORD value is defined.</span></span> <span data-ttu-id="6f3d1-140">다음 스크린샷은 ClearType 수준에 대 한 레지스트리 편집기 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-140">The following screenshot shows the Registry Editor setting for the ClearType level.</span></span>  
  
 ![레지스트리 편집기의 ClearType 설정](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="6f3d1-142">응용 프로그램은 ClearType을 사용 하거나 사용 하지 않고 두 가지 모드 중 하나로 텍스트를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-142">applications render text in one of either two modes, with and without ClearType.</span></span> <span data-ttu-id="6f3d1-143">ClearType 없이 텍스트를 렌더링 하는 경우 회색조 렌더링 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-143">When text is rendered without ClearType, it is referred to as gray scale rendering.</span></span>  
  
<a name="gamma_level"></a>   
## <a name="gamma-level"></a><span data-ttu-id="6f3d1-144">감마 수준</span><span class="sxs-lookup"><span data-stu-id="6f3d1-144">Gamma Level</span></span>  
 <span data-ttu-id="6f3d1-145">감마 수준은 픽셀 값과 광도 사이의 비선형 관계를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-145">The gamma level refers to the nonlinear relationship between a pixel value and luminance.</span></span> <span data-ttu-id="6f3d1-146">감마 수준 설정은 디스플레이 디바이스의 물리적 특성과 일치해야 합니다. 그렇지 않으면 렌더링된 출력에서 왜곡이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-146">The gamma level setting should correspond to the physical characteristics of the display device; otherwise, distortions in rendered output may occur.</span></span> <span data-ttu-id="6f3d1-147">예를 들어 테스트가 너무 넓거나 너무 좁게 나타나거나 문자 모양의 세로 획 가장자리에 색 주름이 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-147">For example, test may appear too wide or too narrow, or color fringes may appear on the edges of vertical stems of glyphs.</span></span>  
  
 <span data-ttu-id="6f3d1-148">감마 수준은 1,000에서 2,200까지의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-148">The gamma level is an integer value that ranges from 1000 to 2200.</span></span> <span data-ttu-id="6f3d1-149">기본 수준은 1,900입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-149">The default level is 1900.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="6f3d1-150">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-150">Registry Setting</span></span>  
 <span data-ttu-id="6f3d1-151">감마 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 디바이스 이름에 해당하는 로컬 컴퓨터 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-151">The registry setting location for the gamma level is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="6f3d1-152">사용자의 각 표시 장치 이름에 대해 `GammaLevel` DWORD 값이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-152">For each display device name for a user, a `GammaLevel` DWORD value is defined.</span></span> <span data-ttu-id="6f3d1-153">다음 스크린샷에서는 감마 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-153">The following screenshot shows the Registry Editor setting for the gamma level.</span></span>  
  
 ![레지스트리 편집기의 ClearType 감마 수준 설정](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="pixel_structure"></a>   
## <a name="pixel-structure"></a><span data-ttu-id="6f3d1-155">픽셀 구조체</span><span class="sxs-lookup"><span data-stu-id="6f3d1-155">Pixel Structure</span></span>  
 <span data-ttu-id="6f3d1-156">픽셀 구조체는 디스플레이 디바이스를 구성하는 픽셀 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-156">The pixel structure describes the type of pixels that make up a display device.</span></span> <span data-ttu-id="6f3d1-157">픽셀 구조체는 다음 세 가지 형식 중 하나로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-157">The pixel structure is defined as one of three types:</span></span>  
  
|<span data-ttu-id="6f3d1-158">형식</span><span class="sxs-lookup"><span data-stu-id="6f3d1-158">Type</span></span>|<span data-ttu-id="6f3d1-159">값</span><span class="sxs-lookup"><span data-stu-id="6f3d1-159">Value</span></span>|<span data-ttu-id="6f3d1-160">설명</span><span class="sxs-lookup"><span data-stu-id="6f3d1-160">Description</span></span>|  
|----------|-----------|-----------------|  
|<span data-ttu-id="6f3d1-161">플랫</span><span class="sxs-lookup"><span data-stu-id="6f3d1-161">Flat</span></span>|<span data-ttu-id="6f3d1-162">0</span><span class="sxs-lookup"><span data-stu-id="6f3d1-162">0</span></span>|<span data-ttu-id="6f3d1-163">디스플레이 디바이스에는 픽셀 구조체가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-163">The display device has no pixel structure.</span></span> <span data-ttu-id="6f3d1-164">즉 각 색의 광원이 픽셀 영역에서 고르게 분산되며, 이를 회색조 렌더링이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-164">This means that light sources for each color are spread equally on the pixel area—this is referred to as gray scale rendering.</span></span> <span data-ttu-id="6f3d1-165">이 형식은 표준 디스플레이 디바이스에서 작동하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-165">This is how a standard display device works.</span></span> <span data-ttu-id="6f3d1-166">ClearType은 렌더링 된 텍스트에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-166">ClearType is never applied to the rendered text.</span></span>|  
|<span data-ttu-id="6f3d1-167">RGB</span><span class="sxs-lookup"><span data-stu-id="6f3d1-167">RGB</span></span>|<span data-ttu-id="6f3d1-168">1</span><span class="sxs-lookup"><span data-stu-id="6f3d1-168">1</span></span>|<span data-ttu-id="6f3d1-169">디스플레이 디바이스에는 빨강, 녹색 및 파랑 순서의 3개 스트라이프로 구성되는 픽셀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-169">The display device has pixels that consist of three stripes in the following order: red, green, and blue.</span></span> <span data-ttu-id="6f3d1-170">ClearType은 렌더링 된 텍스트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-170">ClearType is applied to the rendered text.</span></span>|  
|<span data-ttu-id="6f3d1-171">BGR</span><span class="sxs-lookup"><span data-stu-id="6f3d1-171">BGR</span></span>|<span data-ttu-id="6f3d1-172">2</span><span class="sxs-lookup"><span data-stu-id="6f3d1-172">2</span></span>|<span data-ttu-id="6f3d1-173">디스플레이 디바이스에는 파랑, 녹색 및 빨강 순서의 3개 스트라이프로 구성되는 픽셀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-173">The display device has pixels that consist of three stripes in the following order: blue, green, and red.</span></span> <span data-ttu-id="6f3d1-174">ClearType은 렌더링 된 텍스트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-174">ClearType is applied to the rendered text.</span></span> <span data-ttu-id="6f3d1-175">색의 순서가 RGB 형식과는 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-175">Notice how the order is inverted from the RGB type.</span></span>|  
  
 <span data-ttu-id="6f3d1-176">픽셀 구조체는 0에서 2까지의 정수 값에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-176">The pixel structure corresponds to an integer value that ranges from 0 to 2.</span></span> <span data-ttu-id="6f3d1-177">기본 수준은 플랫 픽셀 구조체를 나타내는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-177">The default level is 0, which represents a flat pixel structure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f3d1-178">표시 장치 이름을 열거 하는 `EnumDisplayDevices` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 방법에 대 한 자세한 내용은 함수를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-178">For information on enumerating display device names, see the `EnumDisplayDevices`[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="6f3d1-179">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-179">Registry Setting</span></span>  
 <span data-ttu-id="6f3d1-180">픽셀 구조체에 대한 레지스트리 설정 위치는 특정 디스플레이 디바이스 이름에 해당하는 로컬 컴퓨터 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-180">The registry setting location for the pixel structure is a local machine setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="6f3d1-181">사용자의 각 표시 장치 이름에 대해 `PixelStructure` DWORD 값이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-181">For each display device name for a user, a `PixelStructure` DWORD value is defined.</span></span> <span data-ttu-id="6f3d1-182">다음 스크린샷에서는 픽셀 구조체에 대한 레지스트리 편집기 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-182">The following screenshot shows the Registry Editor setting for the pixel structure.</span></span>  
  
 ![레지스트리 편집기의 ClearType 감마 수준 설정](./media/cleartype-registry-settings/cleartype-gamma-level-settings-registry-editor.png)  
  
<a name="text_contrast_level"></a>   
## <a name="text-contrast-level"></a><span data-ttu-id="6f3d1-184">텍스트 대비 수준</span><span class="sxs-lookup"><span data-stu-id="6f3d1-184">Text Contrast Level</span></span>  
 <span data-ttu-id="6f3d1-185">텍스트 대비 수준을 사용하면 문자 모양의 획 너비를 기준으로 텍스트 렌더링을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-185">The text contrast level allows you to adjust the rendering of text based on the stem widths of glyphs.</span></span> <span data-ttu-id="6f3d1-186">텍스트 대비 수준은 0에서 6까지의 정수 값이며, 정수 값이 클수록 획이 넓어집니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-186">The text contrast level is an integer value that ranges from 0 to 6—the larger the integer value, the wider the stem.</span></span> <span data-ttu-id="6f3d1-187">기본 수준은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-187">The default level is 1.</span></span>  
  
### <a name="registry-setting"></a><span data-ttu-id="6f3d1-188">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="6f3d1-188">Registry Setting</span></span>  
 <span data-ttu-id="6f3d1-189">텍스트 대비 수준에 대한 레지스트리 설정 위치는 특정 디스플레이 디바이스 이름에 해당하는 개별 사용자 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-189">The registry setting location for the text contrast level is an individual user setting that corresponds to a specific display device name:</span></span>  
  
 `HKEY_CURRENT_USER\Software\Microsoft\Avalon.Graphics\<displayName>`  
  
 <span data-ttu-id="6f3d1-190">사용자의 각 표시 장치 이름에 대해 `TextContrastLevel` DWORD 값이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-190">For each display device name for a user, a `TextContrastLevel` DWORD value is defined.</span></span> <span data-ttu-id="6f3d1-191">다음 스크린샷에서는 텍스트 대조 수준에 대한 레지스트리 편집기 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f3d1-191">The following screenshot shows the Registry Editor setting for the text contrast level.</span></span>  
  
 ![레지스트리 편집기의 ClearType 설정](./media/cleartype-registry-settings/cleartype-settings-registry-editor.png)  
  
## <a name="see-also"></a><span data-ttu-id="6f3d1-193">참고자료</span><span class="sxs-lookup"><span data-stu-id="6f3d1-193">See also</span></span>

- [<span data-ttu-id="6f3d1-194">ClearType 개요</span><span class="sxs-lookup"><span data-stu-id="6f3d1-194">ClearType Overview</span></span>](cleartype-overview.md)
- [<span data-ttu-id="6f3d1-195">ClearType 앤티 앨리어싱</span><span class="sxs-lookup"><span data-stu-id="6f3d1-195">ClearType Antialiasing</span></span>](/windows/desktop/gdi/cleartype-antialiasing)
