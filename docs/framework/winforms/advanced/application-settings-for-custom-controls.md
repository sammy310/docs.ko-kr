---
title: 사용자 지정 컨트롤에 대한 애플리케이션 설정
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: d12caf9ed2cb80d837080badab436b2e9b0b3728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714348"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="c75c7-102">사용자 지정 컨트롤에 대한 애플리케이션 설정</span><span class="sxs-lookup"><span data-stu-id="c75c7-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="c75c7-103">사용자 지정 컨트롤에서 타사 응용 프로그램에서 컨트롤을 호스팅할 때 응용 프로그램 설정을 유지할 수 있도록 특정 작업을 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>  
  
 <span data-ttu-id="c75c7-104">대부분의 응용 프로그램 설정 기능에 대 한 설명서는 독립 실행형 응용 프로그램을 만든다고 가정 아래 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="c75c7-105">그러나 응용 프로그램에서 다른 개발자가 호스트 하는 컨트롤을 만드는 경우 해당 설정을 유지 하 여 컨트롤에 대 한 몇 가지 추가 단계를 수행 하려면 적절 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>  
  
## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="c75c7-106">응용 프로그램 설정 및 사용자 지정 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c75c7-106">Application Settings and Custom Controls</span></span>  
 <span data-ttu-id="c75c7-107">제대로 해당 설정을 유지 하기 위해 컨트롤에 대 한 설정 래퍼 클래스에서 파생 된 고유한 전용된 응용 프로그램을 만들어 프로세스를 캡슐화 해야 것 <xref:System.Configuration.ApplicationSettingsBase>입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="c75c7-108">또한 기본 컨트롤 클래스를 구현 해야 합니다는 <xref:System.Configuration.IPersistComponentSettings>합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="c75c7-109">인터페이스를 두 가지 방법 뿐만 아니라 여러 속성이 포함 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 고 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="c75c7-110">사용 하 여 폼 컨트롤을 추가 하는 경우는 **Windows Forms 디자이너** Visual Studio에서 Windows Forms 호출 <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> 컨트롤이 초기화 될 때 자동으로; 호출 해야 합니다 <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> 보십시오를 `Dispose` 컨트롤의 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>  
  
 <span data-ttu-id="c75c7-111">또한 Visual Studio와 같은 디자인 타임 환경에서 제대로 작동 하려면 사용자 지정 컨트롤에 대 한 응용 프로그램 설정에 대 한 순서에는 다음을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>  
  
1.  <span data-ttu-id="c75c7-112">사용 하는 생성자를 사용 하 여 사용자 지정 응용 프로그램 설정 클래스를 <xref:System.ComponentModel.IComponent> 단일 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="c75c7-113">저장 하 고 모든 응용 프로그램 설정을 로드할이 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="c75c7-114">이 클래스의 새 인스턴스를 만든 경우 생성자를 사용 하 여 사용자 지정 컨트롤을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>  
  
2.  <span data-ttu-id="c75c7-115">컨트롤 생성 및와 같은 폼의 폼에 배치 된 후이 사용자 지정 설정 클래스를 만드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
 <span data-ttu-id="c75c7-116">사용자 지정 설정 클래스를 만드는 방법에 대 한 지침을 참조 하세요. [방법: 응용 프로그램 설정 만들기](how-to-create-application-settings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>  
  
## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="c75c7-117">설정 키 및 공유 설정</span><span class="sxs-lookup"><span data-stu-id="c75c7-117">Settings Keys and Shared Settings</span></span>  
 <span data-ttu-id="c75c7-118">일부 컨트롤은 동일한 폼 내에서 여러 번 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="c75c7-119">대부분의 경우 이러한 컨트롤을 개별 설정을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="c75c7-120">사용 하 여 합니다 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 속성을 <xref:System.Configuration.IPersistComponentSettings>, 폼에서 컨트롤의 여러 버전을 명확 하 게 작동 하는 고유 문자열을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>  
  
 <span data-ttu-id="c75c7-121">구현 하는 가장 간단한 방법은 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 사용 하는 것을 <xref:System.Windows.Forms.Control.Name%2A> 에 대 한 컨트롤의 속성을 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="c75c7-122">값을 전달으로 로드 하거나 컨트롤의 설정을 저장 하는 경우 <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> 에 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 의 속성을 <xref:System.Configuration.ApplicationSettingsBase> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="c75c7-123">XML로 사용자 설정을 유지할 때 고유 키를 사용 하는 응용 프로그램 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="c75c7-124">다음 코드 예제에서는 어떻게를 `<userSettings>` 이라는 사용자 지정 컨트롤의 인스턴스에 대 한 섹션 보일 수 있습니다 `CustomControl1` 에 대 한 설정을 저장 하는 해당 `Text` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <span data-ttu-id="c75c7-125">에 대 한 값을 제공 하지 않는 컨트롤의 모든 인스턴스 <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> 동일한 설정을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c75c7-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75c7-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="c75c7-126">See also</span></span>
- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [<span data-ttu-id="c75c7-127">응용 프로그램 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="c75c7-127">Application Settings Architecture</span></span>](application-settings-architecture.md)
