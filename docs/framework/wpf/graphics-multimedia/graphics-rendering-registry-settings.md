---
title: 그래픽 렌더링 레지스트리 설정
description: Windows Presentation Foundation (WPF)에서 문제 해결, 디버깅 및 제품 지원을 위해 레지스트리 설정을 사용 하는 방법을 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- rendering graphics [WPF], registry settings
- rendering graphics [WPF]
- rendering graphics [WPF], troubleshooting
- troubleshooting graphics rendering [WPF]
- graphics [WPF], rendering
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
ms.openlocfilehash: a2c6cfa5a207ae89c053f6ee81597f01458b5933
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853761"
---
# <a name="graphics-rendering-registry-settings"></a><span data-ttu-id="9c08a-103">그래픽 렌더링 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9c08a-103">Graphics Rendering Registry Settings</span></span>
<span data-ttu-id="9c08a-104">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션에 영향을 미치는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 렌더링 레지스트리 설정에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-104">This topic provides an overview of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics rendering registry settings that affect [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  

<a name="overview"></a>
## <a name="when-to-use-graphics-rendering-registry-settings"></a><span data-ttu-id="9c08a-105">그래픽 렌더링 레지스트리 설정을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="9c08a-105">When to Use Graphics Rendering Registry Settings</span></span>  
 <span data-ttu-id="9c08a-106">이러한 레지스트리 설정은 문제 해결, 디버깅 및 제품 지원 목적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-106">These registry settings are provided for troubleshooting, debugging, and product support purposes.</span></span> <span data-ttu-id="9c08a-107">레지스트리를 변경하면 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션에 영향을 주기 때문에 애플리케이션은 자동으로 또는 설치 중에 이러한 레지스트리 키를 변경하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-107">Because changes to the registry affect all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, your application should never alter these registry keys automatically, or during installation.</span></span>  
  
<a name="xpdmandwddm"></a>
## <a name="what-are-xpdm-and-wddm"></a><span data-ttu-id="9c08a-108">XPDM 및 WDDM이란?</span><span class="sxs-lookup"><span data-stu-id="9c08a-108">What are XPDM and WDDM?</span></span>  
 <span data-ttu-id="9c08a-109">일부 그래픽 렌더링 레지스트리 설정은 비디오 카드가 XPDM 드라이버를 사용하는지 또는 WDDM 드라이버를 사용하는지에 따라 기본값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-109">Some of the graphics rendering registry settings have different default values, depending on whether your video card uses an XPDM or WDDM driver.</span></span> <span data-ttu-id="9c08a-110">XPDM은 Microsoft Windows XP 디스플레이 드라이버 모델 이며, WDDM은 Windows 디스플레이 드라이버 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-110">XPDM is the Microsoft Windows XP Display Driver Model and WDDM is the Windows Display Driver Model.</span></span> <span data-ttu-id="9c08a-111">WDDM은 Windows Vista 및 Windows 7을 실행 하는 컴퓨터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-111">WDDM is available on computers running Windows Vista and Windows 7.</span></span> <span data-ttu-id="9c08a-112">XPDM은 Windows Vista, Microsoft Windows XP 및 Microsoft Windows Server 2003를 실행 하는 컴퓨터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-112">XPDM is available on computers running Windows Vista, Microsoft Windows XP, and Microsoft Windows Server 2003.</span></span> <span data-ttu-id="9c08a-113">WDDM에 대 한 자세한 내용은 [wddm (Windows Display Driver Model) 디자인 가이드](/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c08a-113">For more information about WDDM, see [Windows Display Driver Model (WDDM) Design Guide](/windows-hardware/drivers/display/windows-vista-display-driver-model-design-guide).</span></span>  
  
<a name="registry_settings"></a>
## <a name="registry-settings"></a><span data-ttu-id="9c08a-114">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="9c08a-114">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="9c08a-115">에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링을 제어하는 다음 네 개의 레지스트리 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-115">provides four registry settings for controlling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendering:</span></span>  
  
|<span data-ttu-id="9c08a-116">설정</span><span class="sxs-lookup"><span data-stu-id="9c08a-116">Setting</span></span>|<span data-ttu-id="9c08a-117">설명</span><span class="sxs-lookup"><span data-stu-id="9c08a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c08a-118">**하드웨어 가속 옵션 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="9c08a-118">**Disable Hardware Acceleration Option**</span></span>|<span data-ttu-id="9c08a-119">하드웨어 가속을 사용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-119">Specifies whether hardware acceleration should be enabled.</span></span>|  
|<span data-ttu-id="9c08a-120">**최대 다중 샘플 값**</span><span class="sxs-lookup"><span data-stu-id="9c08a-120">**Maximum Multisample Value**</span></span>|<span data-ttu-id="9c08a-121">앤티 앨리어싱 3D 콘텐츠에 대 한 다중 샘플링 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-121">Specifies the degree of multisampling for antialiasing 3D content.</span></span>|  
|<span data-ttu-id="9c08a-122">**필수 비디오 드라이버 날짜 설정**</span><span class="sxs-lookup"><span data-stu-id="9c08a-122">**Required Video Driver Date Setting**</span></span>|<span data-ttu-id="9c08a-123">시스템에서 2004년 11월 이전에 릴리스된 드라이버의 하드웨어 가속을 사용하지 않게 설정할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-123">Specifies whether the system disables hardware acceleration for drivers released before November 2004.</span></span>|  
|<span data-ttu-id="9c08a-124">**참조 래스터라이저 옵션 사용**</span><span class="sxs-lookup"><span data-stu-id="9c08a-124">**Use Reference Rasterizer Option**</span></span>|<span data-ttu-id="9c08a-125">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 참조 래스터라이저를 사용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-125">Specifies whether [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] should use the reference rasterizer.</span></span>|  
  
 <span data-ttu-id="9c08a-126">이러한 설정은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레지스트리 설정을 참조하는 방법을 아는 외부 구성 유틸리티에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-126">These settings can be accessed by any external configuration utility that knows how to reference the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] registry settings.</span></span> <span data-ttu-id="9c08a-127">이러한 설정은 Windows 레지스트리 편집기를 사용 하 여 값에 직접 액세스 하 여 만들거나 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-127">These settings can also be created or modified by accessing the values directly by using the Windows Registry Editor.</span></span>  
  
<a name="disablehardwareacceleration"></a>
## <a name="disable-hardware-acceleration-option"></a><span data-ttu-id="9c08a-128">하드웨어 가속 옵션 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9c08a-128">Disable Hardware Acceleration Option</span></span>  
  
|<span data-ttu-id="9c08a-129">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="9c08a-129">Registry key</span></span>|<span data-ttu-id="9c08a-130">값 형식</span><span class="sxs-lookup"><span data-stu-id="9c08a-130">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|<span data-ttu-id="9c08a-131">DWORD</span><span class="sxs-lookup"><span data-stu-id="9c08a-131">DWORD</span></span>|  
  
 <span data-ttu-id="9c08a-132">**하드웨어 가속 옵션 사용 안 함**을 사용하여 디버깅 및 테스트 목적으로 하드웨어 가속을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-132">The **disable hardware acceleration option** enables you to turn off hardware acceleration for debugging and test purposes.</span></span> <span data-ttu-id="9c08a-133">애플리케이션에서 렌더링 아티팩트를 표시되면 하드웨어 가속을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="9c08a-133">When you see rendering artifacts in an application, try turning off hardware acceleration.</span></span> <span data-ttu-id="9c08a-134">아티팩트가 사라지면 비디오 드라이버에 문제가 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-134">If the artifact disappears, the problem might be with your video driver.</span></span>  
  
 <span data-ttu-id="9c08a-135">**하드웨어 가속 옵션 사용 안 함**은 0 또는 1의 DWORD 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-135">The **disable hardware acceleration option** is a DWORD value that is either 0 or 1.</span></span> <span data-ttu-id="9c08a-136">이 값이 1이면 하드웨어 가속이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-136">A value of 1 disables hardware acceleration.</span></span> <span data-ttu-id="9c08a-137">이 값이 0이면 시스템이 하드웨어 가속 요구를 충족할 경우 하드웨어 가속이 사용됩니다. 자세한 내용은 [그래픽 렌더링 계층](../advanced/graphics-rendering-tiers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9c08a-137">A value of 0 enables hardware acceleration, provided the system meets hardware acceleration requirements; for more information, see [Graphics Rendering Tiers](../advanced/graphics-rendering-tiers.md).</span></span>  
  
<a name="maxmultisample"></a>
## <a name="maximum-multisample-value"></a><span data-ttu-id="9c08a-138">최대 다중 샘플 값</span><span class="sxs-lookup"><span data-stu-id="9c08a-138">Maximum Multisample Value</span></span>  
  
|<span data-ttu-id="9c08a-139">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="9c08a-139">Registry key</span></span>|<span data-ttu-id="9c08a-140">값 형식</span><span class="sxs-lookup"><span data-stu-id="9c08a-140">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|<span data-ttu-id="9c08a-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="9c08a-141">DWORD</span></span>|  
  
 <span data-ttu-id="9c08a-142">**Maximum 다중 샘플 값** 을 사용 하면 3d 콘텐츠의 최대 앤티 앨리어싱 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-142">The **maximum multisample value** enables you to adjust the maximum amount of antialiasing of 3D content.</span></span> <span data-ttu-id="9c08a-143">Windows Vista에서 3D 앤티 앨리어싱을 사용 하지 않도록 설정 하려면이 수준을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-143">Use this level to disable 3D antialiasing in Windows Vista.</span></span>  
  
 <span data-ttu-id="9c08a-144">**최대 다중 샘플 값**은 0~16 사이의 DWORD 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-144">The **maximum multisample value** is a DWORD value that ranges from 0 to 16.</span></span> <span data-ttu-id="9c08a-145">값이 0 이면 3D 콘텐츠의 다중 샘플 앤티엘리어싱을 사용 하지 않도록 설정 하 고, 값 16은 비디오 카드에서 지 원하는 경우 최대 16x 다중 샘플 앤티엘리어싱을 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-145">A value of 0 specifies that multisample antialiasing of 3D content should be disabled, and a value of 16 will attempt to use up to 16x multisample antialiasing, if supported by the video card.</span></span> <span data-ttu-id="9c08a-146">XPDM 드라이버를 사용 하는 컴퓨터에서이 레지스트리 키 값을 설정 하면 응용 프로그램에서 많은 양의 추가 비디오 메모리를 사용 하 고, 3D 렌더링의 성능을 저하 시키고, 렌더링 오류 및 안정성 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-146">Beware that setting this registry key value on computers using XPDM drivers will cause applications to use a large amount of additional video memory, decrease the performance of 3D rendering, and has the potential to introduce rendering errors and stability problems.</span></span>  
  
 <span data-ttu-id="9c08a-147">이 레지스트리 키가 설정되지 않았으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본값은 XPDM 드라이버의 경우 0, WDDM 드라이버의 경우 4입니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-147">When this registry key is not set, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] defaults to 0 for XPDM drivers and 4 for WDDM drivers.</span></span>  
  
<a name="requiredvideodriverdatesetting"></a>
## <a name="required-video-driver-date-setting"></a><span data-ttu-id="9c08a-148">필수 비디오 드라이버 날짜 설정</span><span class="sxs-lookup"><span data-stu-id="9c08a-148">Required Video Driver Date Setting</span></span>  
  
|<span data-ttu-id="9c08a-149">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="9c08a-149">Registry key</span></span>|<span data-ttu-id="9c08a-150">값 형식</span><span class="sxs-lookup"><span data-stu-id="9c08a-150">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|<span data-ttu-id="9c08a-151">String</span><span class="sxs-lookup"><span data-stu-id="9c08a-151">String</span></span>|  
  
 <span data-ttu-id="9c08a-152">2004 년 11 월에 Microsoft는 새 버전의 드라이버 테스트 지침을 출시 했습니다. 이 날짜 이후에 작성 된 드라이버는 더 나은 안정성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-152">In November, 2004, Microsoft released a new version of the driver testing guidelines; the drivers written after this date offer better stability.</span></span> <span data-ttu-id="9c08a-153">기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 이러한 드라이버에 대해 하드웨어 가속 파이프라인을 사용하며, 이 날짜 이전에 게시된 XPDM 드라이버용 소프트웨어 렌더링으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-153">By default, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] will use the hardware acceleration pipeline for these drivers and will fall back to software rendering for XPDM drivers published before this date.</span></span>  
  
 <span data-ttu-id="9c08a-154">**필수 비디오 드라이버 날짜 설정**을 통해 XPDM 드라이버에 대한 대체 최소 날짜를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-154">The **required video driver date setting** enables you to specify an alternate minimum date for XPDM drivers.</span></span> <span data-ttu-id="9c08a-155">비디오 드라이버가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 지원하기에 충분히 안정적인 경우에만 2004년 11월 이전 날짜를 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-155">You should only specify a date earlier than November, 2004 if you are confident that your video driver is stable enough to support [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="9c08a-156">필수 비디오 드라이버 설정은 다음 형식의 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-156">The required video driver setting takes a string of the following format:</span></span>  
  
| |  
|-|  
|<span data-ttu-id="9c08a-157">*YYYY* `/` *MM* `/` *DD*</span><span class="sxs-lookup"><span data-stu-id="9c08a-157">*YYYY* `/` *MM* `/` *DD*</span></span>|  
  
 <span data-ttu-id="9c08a-158">여기서 *YYYY*는 4자리 연도이고, *MM*은 2자리 월이고, *DD*는 2자리 일입니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-158">Where *YYYY* is the four-digit year, *MM* is the two-digit month, and *DD* is the two digit day.</span></span> <span data-ttu-id="9c08a-159">이 값을 설정하지 않으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 필수 비디오 드라이버 날짜로 2004년 11월을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-159">When this value is unset, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uses November, 2004 as its required video driver date.</span></span>  
  
<a name="usereferencerasterizeroption"></a>
## <a name="use-reference-rasterizer-option"></a><span data-ttu-id="9c08a-160">참조 래스터라이저 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="9c08a-160">Use Reference Rasterizer Option</span></span>  
  
|<span data-ttu-id="9c08a-161">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="9c08a-161">Registry key</span></span>|<span data-ttu-id="9c08a-162">값 형식</span><span class="sxs-lookup"><span data-stu-id="9c08a-162">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|<span data-ttu-id="9c08a-163">DWORD</span><span class="sxs-lookup"><span data-stu-id="9c08a-163">DWORD</span></span>|  
  
 <span data-ttu-id="9c08a-164">**참조 래스터 라이저 사용 옵션** 을 사용 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 디버깅을 위해 시뮬레이션 된 하드웨어 렌더링 모드를 강제 적용할 수 있습니다 .는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하드웨어 모드로 전환 되지만 실제 하드웨어 장치 대신 Microsoft Direct3D 참조 소프트웨어 래스터 라이저 (d3dref9.dll)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-164">The **use reference rasterizer option** enables you to force [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] into a simulated hardware rendering mode for debugging: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] goes into hardware mode, but uses the Microsoft Direct3D reference software rasterizer, d3dref9.dll, instead of an actual hardware device.</span></span>  
  
 <span data-ttu-id="9c08a-165">참조 래스터라이저는 매우 느리지만 비디오 드라이버를 우회하여 드라이버 문제로 인한 렌더링 문제를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-165">The reference rasterizer is very slow, but bypasses your video driver to avoid any rendering issues caused by driver problems.</span></span> <span data-ttu-id="9c08a-166">이러한 이유로 참조 래스터라이저를 사용하여 렌더링 문제가 비디오 드라이버로 인한 것인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-166">For this reason, you can use the reference rasterizer to determine if rendering issues are caused by the video driver.</span></span> <span data-ttu-id="9c08a-167">d3dref9.dll 파일은 시스템 경로의 위치나 애플리케이션의 로컬 디렉터리 같이 애플리케이션이 액세스할 수 있는 위치에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-167">The d3dref9.dll file must be in a location where the application can access it, such as in any location in the system path or in the local directory of the application.</span></span>  
  
 <span data-ttu-id="9c08a-168">**참조 래스터라이저 옵션 사용**은 DWORD 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-168">The **use reference rasterizer option** takes a DWORD value.</span></span> <span data-ttu-id="9c08a-169">값이 0이면 참조 래스터라이저가 사용되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-169">A value of 0 indicates that the reference rasterizer is not used.</span></span> <span data-ttu-id="9c08a-170">0이 아닌 값을 지정하면 강제로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 참조 래스터라이저를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c08a-170">Any other non-zero value forces [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to use the reference rasterizer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c08a-171">참조</span><span class="sxs-lookup"><span data-stu-id="9c08a-171">See also</span></span>

- [<span data-ttu-id="9c08a-172">그래픽 렌더링 계층</span><span class="sxs-lookup"><span data-stu-id="9c08a-172">Graphics Rendering Tiers</span></span>](../advanced/graphics-rendering-tiers.md)
- [<span data-ttu-id="9c08a-173">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="9c08a-173">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
