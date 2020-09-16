---
title: 애플리케이션 구성
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 04ddce4755ce30b7d46c3bd54024af08361d96ad
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536083"
---
# <a name="configuring-your-application"></a><span data-ttu-id="4e1ac-102">애플리케이션 구성</span><span class="sxs-lookup"><span data-stu-id="4e1ac-102">Configuring Your Application</span></span>
<span data-ttu-id="4e1ac-103">WCF (Windows Communication Foundation)는 .NET 구성 시스템을 사용 하 여 컴퓨터 및 응용 프로그램 범위에서 서비스를 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="4e1ac-104">WCF에서 정의한 구성 설정은 섹션 그룹에 있습니다 `<system.serviceModel>` .</span><span class="sxs-lookup"><span data-stu-id="4e1ac-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="4e1ac-105">WCF 서비스를 구성 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="4e1ac-106">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="4e1ac-106">Configuring Services</span></span>](../configuring-services.md)  
  
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="4e1ac-107">애플리케이션에서 정의한 구성 설정은 `<appSettings>` 섹션 그룹에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-107">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="4e1ac-108">.NET 구성 파일의 응용 프로그램 설정에 대 한 자세한 내용은을 참조 하십시오 [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)) .</span><span class="sxs-lookup"><span data-stu-id="4e1ac-108">For more information about application settings in .NET configuration files, see [\<appSettings>](/previous-versions/dotnet/netframework-4.0/ms228154(v=vs.100)).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="4e1ac-109">Configuration Editor 사용</span><span class="sxs-lookup"><span data-stu-id="4e1ac-109">Using the Configuration Editor</span></span>  
 <span data-ttu-id="4e1ac-110">WCF [구성 편집기 도구 (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) 를 사용 하면 관리자와 개발자가 그래픽 사용자 인터페이스를 사용 하 여 WCF 서비스의 구성 설정을 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-110">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="4e1ac-111">이 도구를 사용 하면 XML 구성 파일을 직접 편집 하지 않고도 WCF 바인딩, 동작, 서비스 및 진단에 대 한 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-111">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="4e1ac-112">Visual Studio에서 구성 파일 편집</span><span class="sxs-lookup"><span data-stu-id="4e1ac-112">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="4e1ac-113">Visual Studio에서 WCF 서비스 프로젝트의 구성 파일을 편집 하려면 **솔루션 탐색기** 에서 해당 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **wcf 구성 편집** 상황에 맞는 메뉴 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-113">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="4e1ac-114">[구성 편집기 도구 (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md)가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-114">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e1ac-115">**솔루션 탐색기**에서 Visual Studio를 마우스 오른쪽 단추로 클릭 하 여 Wcf 웹 서비스 프로젝트의 구성 파일을 편집 하는 경우 **wcf 구성 편집** 상황에 맞는 메뉴 항목이 누락 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-115">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="4e1ac-116">이 문제를 해결 하려면 **도구** 메뉴를 클릭 하 고 **WCF 서비스 구성 편집기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-116">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="4e1ac-117">그런 다음 구성 파일을 마우스 오른쪽 단추로 클릭 하 고 **WCF 구성 편집** 상황에 맞는 메뉴 항목을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e1ac-117">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e1ac-118">참조</span><span class="sxs-lookup"><span data-stu-id="4e1ac-118">See also</span></span>

- [<span data-ttu-id="4e1ac-119">Configuration Editor 도구(SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="4e1ac-119">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="4e1ac-120">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="4e1ac-120">Configuring Services</span></span>](../configuring-services.md)
- [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)
