---
title: 사용자 지정 컨트롤에 대한 애플리케이션 설정
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: a4e477ce1c171b514482623595b2c5565564a2cb
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040469"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="bef43-102">사용자 지정 컨트롤에 대한 애플리케이션 설정</span><span class="sxs-lookup"><span data-stu-id="bef43-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="bef43-103">컨트롤이 타사 응용 프로그램에서 호스팅될 때 응용 프로그램 설정을 유지 하는 기능을 사용자 지정 컨트롤에 제공 하려면 특정 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>

 <span data-ttu-id="bef43-104">응용 프로그램 설정 기능에 대 한 대부분의 설명서는 독립 실행형 응용 프로그램을 만드는 것으로 가정 하 여 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="bef43-105">그러나 다른 개발자가 자신의 응용 프로그램에서 호스팅하는 컨트롤을 만드는 경우에는 컨트롤의 설정을 적절히 유지 하기 위해 몇 가지 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>

## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="bef43-106">응용 프로그램 설정 및 사용자 지정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bef43-106">Application Settings and Custom Controls</span></span>
 <span data-ttu-id="bef43-107">컨트롤의 설정을 제대로 유지 하려면에서 <xref:System.Configuration.ApplicationSettingsBase>파생 된 고유한 전용 응용 프로그램 설정 래퍼 클래스를 만들어 프로세스를 캡슐화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="bef43-108">또한 주 컨트롤 클래스는를 <xref:System.Configuration.IPersistComponentSettings>구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="bef43-109">인터페이스에는 및 라는 두 가지 메서드를 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 비롯 한 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>여러 속성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="bef43-110">Visual Studio에서 **Windows Forms 디자이너** 를 사용 하 여 폼에 컨트롤을 추가 하는 경우 컨트롤을 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 초기화할 때 Windows Forms가 자동으로 호출 됩니다. 컨트롤 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 의 `Dispose` 메서드에서 직접 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>

 <span data-ttu-id="bef43-111">또한 사용자 지정 컨트롤에 대 한 응용 프로그램 설정이 Visual Studio와 같은 디자인 타임 환경에서 제대로 작동 하도록 하려면 다음을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>

1. <span data-ttu-id="bef43-112">을 단일 매개 변수로 사용 <xref:System.ComponentModel.IComponent> 하는 생성자가 포함 된 사용자 지정 응용 프로그램 설정 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="bef43-113">이 클래스를 사용 하 여 모든 응용 프로그램 설정을 저장 하 고 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="bef43-114">이 클래스의 새 인스턴스를 만들 때 생성자를 사용 하 여 사용자 지정 컨트롤을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>

2. <span data-ttu-id="bef43-115">컨트롤이 만들어지고 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기 등의 폼에 배치 된 후이 사용자 지정 설정 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>

 <span data-ttu-id="bef43-116">사용자 지정 설정 클래스를 만드는 방법에 대 한 [자세한 내용은 방법: 응용 프로그램 설정을](how-to-create-application-settings.md)만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>

## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="bef43-117">설정 키 및 공유 설정</span><span class="sxs-lookup"><span data-stu-id="bef43-117">Settings Keys and Shared Settings</span></span>
 <span data-ttu-id="bef43-118">일부 컨트롤은 같은 폼 내에서 여러 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="bef43-119">대부분의 경우 이러한 컨트롤은 자체의 개별 설정을 유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="bef43-120"><xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 의<xref:System.Configuration.IPersistComponentSettings>속성을 사용 하 여 폼에서 여러 버전의 컨트롤을 명확 하 게 구분 하는 고유한 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>

 <span data-ttu-id="bef43-121">을 구현 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 하는 가장 간단한 방법은에 대해 <xref:System.Windows.Forms.Control.Name%2A> 컨트롤 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>의 속성을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="bef43-122">컨트롤의 설정을 로드 하거나 저장 하는 경우의 값 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 을 <xref:System.Configuration.ApplicationSettingsBase> 클래스의 속성에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="bef43-123">응용 프로그램 설정은 사용자의 설정을 XML로 유지 하는 경우이 고유 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="bef43-124">다음 코드 예제에서는 섹션에서 `<userSettings>` 해당 `Text` 속성에 대 한 설정을 저장 하는 이라는 `CustomControl1` 사용자 지정 컨트롤의 인스턴스를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>

```xml
<userSettings>
    <CustomControl1>
        <setting name="Text" serializedAs="string">
            <value>Hello, World</value>
        </setting>
    </CustomControl1>
</userSettings>
```

 <span data-ttu-id="bef43-125">에 대 한 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 값을 제공 하지 않는 컨트롤의 모든 인스턴스는 동일한 설정을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef43-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="bef43-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="bef43-126">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [<span data-ttu-id="bef43-127">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="bef43-127">Application Settings Architecture</span></span>](application-settings-architecture.md)
