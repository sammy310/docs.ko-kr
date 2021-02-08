---
description: '자세한 정보: COM + 서비스 모델 구성 도구 (ComSvcConfig.exe)'
title: COM+ 서비스 모델 구성 도구(ComSvcConfig.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM+ integration
- WCF, COM+ integration
ms.assetid: 7717c6c2-85fc-418b-a8ed-bad8e61cec5c
ms.openlocfilehash: 81bfcbd468cb5401646a49967b6381b48e2f7cf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781066"
---
# <a name="com-service-model-configuration-tool-comsvcconfigexe"></a><span data-ttu-id="fbbf9-103">COM+ 서비스 모델 구성 도구(ComSvcConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="fbbf9-103">COM+ Service Model Configuration Tool (ComSvcConfig.exe)</span></span>

<span data-ttu-id="fbbf9-104">COM+ 서비스 모델 구성 명령줄 도구(ComSvcConfig.exe)를 사용하면 COM+ 인터페이스를 웹 서비스로 노출하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-104">The COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) enables you to configure COM+ interfaces to be exposed as Web services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbbf9-105">구문</span><span class="sxs-lookup"><span data-stu-id="fbbf9-105">Syntax</span></span>  
  
```console  
ComSvcConfig.exe /install | /uninstall | /list [/application:<ApplicationID | ApplicationName>] [/contract:<ClassID | ProgID | *,InterfaceID | InterfaceName | *>] [/hosting:<complus | was>] [/webSite:<WebsiteName>] [/webDirectory:<WebDirectoryName>] [/mex] [/id] [/nologo] [/verbose] [/help] [/partial]  
```  
  
## <a name="remarks"></a><span data-ttu-id="fbbf9-106">설명</span><span class="sxs-lookup"><span data-stu-id="fbbf9-106">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbbf9-107">ComSvcConfig.exe를 사용하려면 로컬 컴퓨터의 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-107">You must be an administrator on the local computer to use ComSvcConfig.exe.</span></span>  
  
 <span data-ttu-id="fbbf9-108">이 도구는 다음 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-108">The tool can be found in the following location</span></span>  
  
 <span data-ttu-id="fbbf9-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="fbbf9-109">%SystemRoot%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation</span></span>\  
  
 <span data-ttu-id="fbbf9-110">ComSvcConfig.exe에 대 한 자세한 내용은 [방법: COM + 서비스 모델 구성 도구 사용](./feature-details/how-to-use-the-com-service-model-configuration-tool.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-110">For more information about ComSvcConfig.exe, see [How to: Use the COM+ Service Model Configuration Tool](./feature-details/how-to-use-the-com-service-model-configuration-tool.md).</span></span>  
  
 <span data-ttu-id="fbbf9-111">다음 표에서는 ComSvcConfig.exe에 사용할 수 있는 모드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-111">The following table describes the modes that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="fbbf9-112">옵션</span><span class="sxs-lookup"><span data-stu-id="fbbf9-112">Option</span></span>|<span data-ttu-id="fbbf9-113">설명</span><span class="sxs-lookup"><span data-stu-id="fbbf9-113">Description</span></span>|  
|------------|-----------------|  
|`install`|<span data-ttu-id="fbbf9-114">서비스 모델 통합을 위해 COM+ 인터페이스에 대한 구성을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-114">Installs a configuration for a COM+ interface for Service Model integration.</span></span><br /><br /> <span data-ttu-id="fbbf9-115">약식은 `/i`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-115">Short form `/i`.</span></span>|  
|`uninstall`|<span data-ttu-id="fbbf9-116">서비스 모델 통합에서 COM+ 인터페이스에 대한 구성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-116">Uninstalls a configuration for a COM+ interface from Service Model integration.</span></span><br /><br /> <span data-ttu-id="fbbf9-117">약식은 `/u`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-117">Short form `/u`.</span></span>|  
|`list`|<span data-ttu-id="fbbf9-118">서비스 모델 통합을 위해 구성된 인터페이스가 있는 COM+ 애플리케이션 및 구성 요소에 대한 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-118">Lists information about COM+ applications and components that have interfaces that are configured for Service Model integration.</span></span><br /><br /> <span data-ttu-id="fbbf9-119">약식은 `/l`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-119">Short form `/l`.</span></span>|  
  
 <span data-ttu-id="fbbf9-120">다음 표에서는 ComSvcConfig.exe에 사용할 수 있는 플래그에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-120">The following table describes the flags that can be used with ComSvcConfig.exe.</span></span>  
  
|<span data-ttu-id="fbbf9-121">옵션</span><span class="sxs-lookup"><span data-stu-id="fbbf9-121">Option</span></span>|<span data-ttu-id="fbbf9-122">설명</span><span class="sxs-lookup"><span data-stu-id="fbbf9-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fbbf9-123">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span><span class="sxs-lookup"><span data-stu-id="fbbf9-123">`/application:` \<*ApplicationID* &#124; *ApplicationName*\></span></span>|<span data-ttu-id="fbbf9-124">구성할 COM+ 애플리케이션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-124">Specifies the COM+ application to configure.</span></span><br /><br /> <span data-ttu-id="fbbf9-125">약식은 `/a`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-125">Short form `/a`.</span></span>|  
|<span data-ttu-id="fbbf9-126">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span><span class="sxs-lookup"><span data-stu-id="fbbf9-126">`/contract:` \<*ClassID*  &#124; *ProgID*  &#124; \*,*InterfaceID* &#124; *InterfaceName* &#124; \*\></span></span>|<span data-ttu-id="fbbf9-127">서비스의 계약으로 구성할 COM+ 구성 요소 및 인터페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-127">Specifies the COM+ component and interface that will be configured as the contract for the service.</span></span><br /><br /> <span data-ttu-id="fbbf9-128">약식은 `/c`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-128">Short form `/c`.</span></span><br /><br /> <span data-ttu-id="fbbf9-129">\*구성 요소 및 인터페이스 이름을 지정할 때 와일드 카드 문자 ()를 사용할 수 있지만 의도 하지 않은 인터페이스를 노출할 수 있기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-129">While the wildcard character (\*) can be used when you specify the component and interface names, we recommend that you do not use it, because you might expose interfaces that you did not intend to.</span></span>|  
|<span data-ttu-id="fbbf9-130">`/hosting:` \<*complus*  &#124; *was*\></span><span class="sxs-lookup"><span data-stu-id="fbbf9-130">`/hosting:` \<*complus*  &#124; *was*\></span></span>|<span data-ttu-id="fbbf9-131">COM+ 호스팅 모드 또는 웹 호스팅 모드를 사용할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-131">Specifies whether to use the COM+ hosting mode or the Web hosting mode.</span></span><br /><br /> <span data-ttu-id="fbbf9-132">약식은 `/h`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-132">Short form `/h`.</span></span><br /><br /> <span data-ttu-id="fbbf9-133">COM+ 호스팅 모드를 사용하려면 COM+ 애플리케이션을 명시적으로 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-133">Using the COM+ hosting mode requires explicit activation of the COM+ application.</span></span> <span data-ttu-id="fbbf9-134">웹 호스팅 모드를 사용하면 필요에 따라 COM+ 애플리케이션을 자동으로 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-134">Using the Web hosting mode allows the COM+ application to be automatically activated as required.</span></span> <span data-ttu-id="fbbf9-135">COM+ 애플리케이션이 라이브러리 애플리케이션인 경우 IIS(인터넷 정보 서비스) 프로세스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-135">If the COM+ application is a library application, it runs in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="fbbf9-136">COM+ 애플리케이션이 서버 애플리케이션인 경우 Dllhost.exe 프로세스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-136">If the COM+ application is a server application, it runs in the Dllhost.exe process.</span></span>|  
|<span data-ttu-id="fbbf9-137">`/webSite:` \<*WebsiteName*\></span><span class="sxs-lookup"><span data-stu-id="fbbf9-137">`/webSite:` \<*WebsiteName*\></span></span>|<span data-ttu-id="fbbf9-138">웹 호스팅 모드를 사용할 때 호스팅할 웹 사이트를 지정합니다. `/hosting` 플래그를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-138">Specifies the Web site for hosting when Web hosting mode is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="fbbf9-139">약식은 `/w`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-139">Short form `/w`.</span></span><br /><br /> <span data-ttu-id="fbbf9-140">웹 사이트가 지정되지 않은 경우에는 기본 웹 사이트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-140">If no Web site is specified, the default Web site is used.</span></span>|  
|<span data-ttu-id="fbbf9-141">`/webDirectory:` \<*WebDirectoryName*\></span><span class="sxs-lookup"><span data-stu-id="fbbf9-141">`/webDirectory:` \<*WebDirectoryName*\></span></span>|<span data-ttu-id="fbbf9-142">웹 호스팅을 사용할 때 호스팅할 가상 디렉터리를 지정합니다. `/hosting` 플래그를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-142">Specifies the virtual directory for hosting when Web hosting is used (see the `/hosting` flag).</span></span><br /><br /> <span data-ttu-id="fbbf9-143">약식은 `/d`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-143">Short form `/d`.</span></span>|  
|`/mex`|<span data-ttu-id="fbbf9-144">서비스에서 계약 정의를 검색하려는 클라이언트를 지원하기 위해 기본 서비스 구성에 MEX(메타데이터 교환) 서비스 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-144">Adds a Metadata Exchange (MEX) service endpoint to the default service configuration to support clients that want to retrieve a contract definition from the service.</span></span><br /><br /> <span data-ttu-id="fbbf9-145">약식은 `/x`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-145">Short form `/x`.</span></span>|  
|`/id`|<span data-ttu-id="fbbf9-146">애플리케이션, 구성 요소 및 인터페이스 정보를 ID로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-146">Displays the application, component, and interface information as IDs.</span></span><br /><br /> <span data-ttu-id="fbbf9-147">약식은 `/k`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-147">Short form `/k`.</span></span>|  
|`/nologo`|<span data-ttu-id="fbbf9-148">ComSvcConfig.exe에서 로고가 표시되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-148">Prevents ComSvcConfig.exe from displaying its logo.</span></span><br /><br /> <span data-ttu-id="fbbf9-149">약식은 `/n`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-149">Short form `/n`.</span></span>|  
|`/verbose`|<span data-ttu-id="fbbf9-150">발생한 모든 오류 이외에 경고 또는 정보 텍스트를 모두 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-150">Outputs all warnings or informational text in addition to any errors encountered.</span></span><br /><br /> <span data-ttu-id="fbbf9-151">약식은 `/v`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-151">Short form `/v`.</span></span>|  
|`/help`|<span data-ttu-id="fbbf9-152">사용 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-152">Displays the usage message.</span></span><br /><br /> <span data-ttu-id="fbbf9-153">약식은 `/?`입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-153">Short form `/?`.</span></span>|  
|`/partial`|<span data-ttu-id="fbbf9-154">지정한 인터페이스에 노출할 수 있는 하나 이상의 메서드 서명이 있는 경우 서비스 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-154">Generates a service configuration when the specified interface includes one or more method signatures that can be exposed.</span></span> <span data-ttu-id="fbbf9-155">서비스 초기화 시 호환되는 메서드는 서비스 계약에 작업으로 나타나며 호환되지 않는 메서드는 무시되고 서비스 계약에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-155">At service initialization time, compatible methods appear as operations on the service contract, and non-compatible methods are ignored and absent from the service contract.</span></span><br /><br /> <span data-ttu-id="fbbf9-156">이 플래그가 없으면 지정한 인터페이스에 하나 이상의 호환되지 않는 메서드가 있는 경우 도구에서 서비스 구성을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-156">If this flag is missing, the tool will not generate a service configuration when the specified interface includes one or more incompatible methods.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="fbbf9-157">예</span><span class="sxs-lookup"><span data-stu-id="fbbf9-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="fbbf9-158">Description</span><span class="sxs-lookup"><span data-stu-id="fbbf9-158">Description</span></span>  

 <span data-ttu-id="fbbf9-159">다음 예제는 OnlineStore COM+ 애플리케이션에 있는 `IFinances` 구성 요소의 `ItemOrders.IFinancial` 인터페이스를 웹 서비스로 노출되는 인터페이스 집합에 COM+ 호스팅 모드를 사용하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-159">The following example adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that are exposed as Web services, using the COM+ hosting mode.</span></span> <span data-ttu-id="fbbf9-160">발생한 모든 오류 이외에 경고를 모두 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-160">All warnings will be output in addition to any errors encountered.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fbbf9-161">코드</span><span class="sxs-lookup"><span data-stu-id="fbbf9-161">Code</span></span>  
  
```console  
ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
```  
  
### <a name="description"></a><span data-ttu-id="fbbf9-162">Description</span><span class="sxs-lookup"><span data-stu-id="fbbf9-162">Description</span></span>  

 <span data-ttu-id="fbbf9-163">다음 예제는 OnlineWarehouse COM+ 애플리케이션에 있는 `IStockLevels` 구성 요소의 `ItemInventory.Warehouse` 인터페이스를 웹 서비스로 노출되는 인터페이스 집합에 웹 호스팅 모드를 사용하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-163">The following example adds the `IStockLevels` interface of the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that are exposed as Web services, using the Web hosting mode.</span></span> <span data-ttu-id="fbbf9-164">웹 서비스는 IIS의 OnlineWarehouse 가상 디렉터리에서 웹 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-164">The Web service is Web hosted in the OnlineWarehouse virtual directory of IIS.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fbbf9-165">코드</span><span class="sxs-lookup"><span data-stu-id="fbbf9-165">Code</span></span>  
  
```console  
ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse  
```  
  
### <a name="description"></a><span data-ttu-id="fbbf9-166">Description</span><span class="sxs-lookup"><span data-stu-id="fbbf9-166">Description</span></span>  

 <span data-ttu-id="fbbf9-167">다음 예제는 OnlineStore COM+ 애플리케이션에 있는 `IFinances` 구성 요소의 `ItemOrders.Financial` 인터페이스를 웹 서비스로 노출되는 인터페이스 집합에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-167">The following example removes the `IFinances` interface of the `ItemOrders.Financial` component (from the OnlineStore COM+ application) from the set of interfaces that are exposed as Web services.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fbbf9-168">코드</span><span class="sxs-lookup"><span data-stu-id="fbbf9-168">Code</span></span>  
  
```console  
ComSvcConfig.exe /uninstall /application:OnlineStore /interface:ItemOrders.Financial,IFinances /hosting:complus  
```  
  
### <a name="description"></a><span data-ttu-id="fbbf9-169">Description</span><span class="sxs-lookup"><span data-stu-id="fbbf9-169">Description</span></span>  

 <span data-ttu-id="fbbf9-170">다음 예제는 현재 노출된 COM+ 호스팅 인터페이스와 함께 로컬 컴퓨터의 OnlineStore COM+ 애플리케이션에 대한 해당 주소 및 바인딩 세부 내용을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbf9-170">The following example lists currently exposed COM+ hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fbbf9-171">코드</span><span class="sxs-lookup"><span data-stu-id="fbbf9-171">Code</span></span>  
  
```console  
ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbbf9-172">참조</span><span class="sxs-lookup"><span data-stu-id="fbbf9-172">See also</span></span>

- [<span data-ttu-id="fbbf9-173">방법: COM+ 서비스 모델 구성 도구 사용</span><span class="sxs-lookup"><span data-stu-id="fbbf9-173">How to: Use the COM+ Service Model Configuration Tool</span></span>](./feature-details/how-to-use-the-com-service-model-configuration-tool.md)
