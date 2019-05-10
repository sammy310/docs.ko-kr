---
title: 응용 프로그램 구성
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 9a1365bb567c552fb087e67a10e48fe0bc2da873
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64652031"
---
# <a name="configuring-your-application"></a><span data-ttu-id="fbac4-102">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="fbac4-102">Configuring Your Application</span></span>
<span data-ttu-id="fbac4-103">Windows Communication Foundation (WCF).NET 구성 시스템을 사용 하 고 컴퓨터 및 응용 프로그램 범위에서 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-103">Windows Communication Foundation (WCF) uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="fbac4-104">WCF에서 정의한 구성 설정은 `<system.serviceModel>` 섹션 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-104">Configuration settings defined by WCF are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="fbac4-105">WCF 서비스를 구성 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbac4-105">For more information about how to configure a WCF service, see the following topics:</span></span>  
  
- [<span data-ttu-id="fbac4-106">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="fbac4-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
- [<span data-ttu-id="fbac4-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fbac4-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="fbac4-108">응용 프로그램에서 정의한 구성 설정은 `<appSettings>` 섹션 그룹에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="fbac4-109">.NET 구성 파일에서 응용 프로그램 설정에 대 한 자세한 내용은 참조 하세요. [ \<appSettings >](https://go.microsoft.com/fwlink/?LinkId=95159)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-109">For more information about application settings in .NET configuration files, see [\<appSettings>](https://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="fbac4-110">Configuration Editor 사용</span><span class="sxs-lookup"><span data-stu-id="fbac4-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="fbac4-111">WCF [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 관리자와 개발자가 그래픽 사용자 인터페이스를 사용 하 여 WCF 서비스에 대 한 구성 설정을 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-111">The WCF [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="fbac4-112">이 도구를 사용 하 여 XML 구성 파일을 직접 편집 하지 않고도 WCF 바인딩, 동작, 서비스 및 진단에 대 한 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-112">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="fbac4-113">Visual Studio에서 구성 파일 편집</span><span class="sxs-lookup"><span data-stu-id="fbac4-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="fbac4-114">Visual Studio에서 WCF 서비스 프로젝트의 구성 파일을 편집 하려면 마우스 오른쪽 단추로 클릭에 **솔루션 탐색기** 선택 합니다 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-114">To edit the configuration file of a WCF service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="fbac4-115">그러면 합니다 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbac4-116">마우스 오른쪽 단추로 클릭 하 여 Visual Studio에서 WCF 웹 서비스 프로젝트의 구성 파일을 편집 하는 경우 **솔루션 탐색기**, 있음을 합니다 **WCF 구성 편집** 상황에 맞는 메뉴 항목이 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-116">If you edit the configuration file of a WCF Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="fbac4-117">문제를 해결 하려면이 문제를 클릭 합니다 **도구** 메뉴에서 선택한 **WCF 서비스 구성 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="fbac4-118">그 후 구성 파일을 마우스 오른쪽 단추로 클릭 하 사용할 수는 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fbac4-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbac4-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="fbac4-119">See also</span></span>

- [<span data-ttu-id="fbac4-120">Configuration Editor 도구(SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="fbac4-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)
- [<span data-ttu-id="fbac4-121">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="fbac4-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)
- [<span data-ttu-id="fbac4-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fbac4-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
