---
title: In-Process Side-by-Side 실행
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 5ca2f03576946a23b3133bbe7532d46c4ad758ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181659"
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="b7f99-102">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="b7f99-102">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="b7f99-103">.NET Framework 4부터 In-Process Side-By-Side 호스팅을 사용하여 단일 프로세스에서 여러 버전의 CLR(공용 언어 런타임)을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-103">Starting with the .NET Framework 4, you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="b7f99-104">기본적으로 관리되는 COM 구성 요소는 프로세스에 대해 로드된 .NET Framework 버전에 관계없이 빌드 시 사용된 .NET Framework 버전을 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-104">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="b7f99-105">배경</span><span class="sxs-lookup"><span data-stu-id="b7f99-105">Background</span></span>  
 <span data-ttu-id="b7f99-106">.NET Framework는 관리 코드 애플리케이션에 대해 항상 병렬 호스팅을 제공하지만 .NET Framework 4 이전에는 관리되는 COM 구성 요소에 대해 해당 기능을 제공하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-106">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the .NET Framework 4, it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="b7f99-107">과거에는 프로세스에 로드된 관리되는 COM 구성 요소를 이미 로드된 런타임 버전 또는 설치된 최신 버전의 .NET Framework로 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-107">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="b7f99-108">이 버전이 COM 구성 요소와 호환되지 않으면 구성 요소가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-108">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="b7f99-109">.NET Framework 4에서는 다음을 보장하는 병렬 호스팅에 대한 새로운 접근 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-109">The .NET Framework 4 provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
- <span data-ttu-id="b7f99-110">새로운 버전의 .NET Framework를 설치해도 기존 애플리케이션에는 영향이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-110">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
- <span data-ttu-id="b7f99-111">빌드 시 사용된 .NET Framework 버전에 대해 애플리케이션이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-111">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="b7f99-112">명시적으로 지정되지 않은 경우 새로운 버전의 .NET Framework를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-112">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="b7f99-113">그러나 애플리케이션이 새로운 버전의 .NET Framework 사용으로 전환하는 것이 더 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-113">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="b7f99-114">사용자와 개발자에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="b7f99-114">Effects on Users and Developers</span></span>  
  
- <span data-ttu-id="b7f99-115">**최종 사용자 및 시스템 관리자**.</span><span class="sxs-lookup"><span data-stu-id="b7f99-115">**End users and system administrators**.</span></span> <span data-ttu-id="b7f99-116">이제 이러한 사용자가 독립적으로 또는 애플리케이션을 사용하여 새로운 버전의 런타임을 설치할 때 컴퓨터에 영향을 주지 않을 것을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-116">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="b7f99-117">기존 애플리케이션은 예전과 같이 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-117">Existing applications will continue to run as they did before.</span></span>  
  
- <span data-ttu-id="b7f99-118">**애플리케이션 개발자**.</span><span class="sxs-lookup"><span data-stu-id="b7f99-118">**Application developers**.</span></span> <span data-ttu-id="b7f99-119">병렬 호스팅은 애플리케이션 개발자에게 거의 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-119">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="b7f99-120">기본적으로 애플리케이션은 항상 빌드 시 사용된 .NET Framework 버전에서 실행되며, 이 동작은 변경되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-120">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="b7f99-121">그러나 개발자가 이 동작을 재정의하고 애플리케이션이 최신 버전의 .NET Framework에서 실행되도록 지정할 수 있습니다([시나리오 2](#scenarios) 참조).</span><span class="sxs-lookup"><span data-stu-id="b7f99-121">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
- <span data-ttu-id="b7f99-122">**라이브러리 개발자 및 소비자**.</span><span class="sxs-lookup"><span data-stu-id="b7f99-122">**Library developers and consumers**.</span></span> <span data-ttu-id="b7f99-123">병렬 호스팅은 라이브러리 개발자가 직면하는 호환성 문제를 해결하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-123">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="b7f99-124">직접 참조를 통해 또는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 호출을 통해 애플리케이션에서 직접 로드하는 라이브러리는 로드된 <xref:System.AppDomain>의 런타임을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-124">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="b7f99-125">지원하려는 모든 버전의 .NET Framework에 대해 라이브러리를 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-125">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="b7f99-126">.NET Framework 4 런타임을 사용하여 애플리케이션이 컴파일되었지만 이전 런타임을 사용하여 빌드된 라이브러리를 포함하는 경우 해당 라이브러리는 .NET Framework 4 런타임도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-126">If an application is compiled using the .NET Framework 4 runtime but includes a library that was built using an earlier runtime, that library will use the .NET Framework 4 runtime as well.</span></span> <span data-ttu-id="b7f99-127">그러나 이전 런타임을 사용하여 빌드된 애플리케이션과 .NET Framework 4를 사용하여 빌드된 라이브러리가 있는 경우 애플리케이션이 .NET Framework 4도 사용하도록 강제 적용해야 합니다([시나리오 3](#scenarios) 참조).</span><span class="sxs-lookup"><span data-stu-id="b7f99-127">However, if you have an application that was built using an earlier runtime and a library that was built using the .NET Framework 4, you must force your application to also use the .NET Framework 4 (see [scenario 3](#scenarios)).</span></span>  
  
- <span data-ttu-id="b7f99-128">**관리되는 COM 구성 요소 개발자**.</span><span class="sxs-lookup"><span data-stu-id="b7f99-128">**Managed COM component developers**.</span></span> <span data-ttu-id="b7f99-129">과거에는 관리되는 COM 구성 요소가 자동으로 컴퓨터에 설치된 최신 버전의 런타임을 사용하여 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-129">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="b7f99-130">이제 빌드 시 사용된 런타임 버전에서 COM 구성 요소를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-130">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="b7f99-131">다음 표와 같이 .NET Framework 버전 1.1로 빌드된 구성 요소를 버전 4 구성 요소와 함께 나란히 실행할 수 있지만 버전 2.0, 3.0 또는 3.5 구성 요소의 경우 해당 버전에 병렬 호스팅을 사용할 수 없기 때문에 병렬 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-131">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="b7f99-132">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="b7f99-132">.NET Framework version</span></span>|<span data-ttu-id="b7f99-133">1.1</span><span class="sxs-lookup"><span data-stu-id="b7f99-133">1.1</span></span>|<span data-ttu-id="b7f99-134">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="b7f99-134">2.0 - 3.5</span></span>|<span data-ttu-id="b7f99-135">4</span><span class="sxs-lookup"><span data-stu-id="b7f99-135">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="b7f99-136">1.1</span><span class="sxs-lookup"><span data-stu-id="b7f99-136">1.1</span></span>|<span data-ttu-id="b7f99-137">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="b7f99-137">Not applicable</span></span>|<span data-ttu-id="b7f99-138">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f99-138">No</span></span>|<span data-ttu-id="b7f99-139">예</span><span class="sxs-lookup"><span data-stu-id="b7f99-139">Yes</span></span>|  
    |<span data-ttu-id="b7f99-140">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="b7f99-140">2.0 - 3.5</span></span>|<span data-ttu-id="b7f99-141">아니요</span><span class="sxs-lookup"><span data-stu-id="b7f99-141">No</span></span>|<span data-ttu-id="b7f99-142">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="b7f99-142">Not applicable</span></span>|<span data-ttu-id="b7f99-143">예</span><span class="sxs-lookup"><span data-stu-id="b7f99-143">Yes</span></span>|  
    |<span data-ttu-id="b7f99-144">4</span><span class="sxs-lookup"><span data-stu-id="b7f99-144">4</span></span>|<span data-ttu-id="b7f99-145">예</span><span class="sxs-lookup"><span data-stu-id="b7f99-145">Yes</span></span>|<span data-ttu-id="b7f99-146">예</span><span class="sxs-lookup"><span data-stu-id="b7f99-146">Yes</span></span>|<span data-ttu-id="b7f99-147">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="b7f99-147">Not applicable</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="b7f99-148">.NET Framework 버전 3.0 및 3.5는 버전 2.0에서 증분 방식으로 빌드되었으며 병렬 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-148">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="b7f99-149">이들은 기본적으로 동일한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-149">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="b7f99-150">일반적인 병렬 호스팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="b7f99-150">Common Side-by-Side Hosting Scenarios</span></span>  
  
- <span data-ttu-id="b7f99-151">**시나리오 1:** 이전 버전의 .NET Framework를 사용하여 빌드된 COM 구성 요소를 사용하는 네이티브 애플리케이션.</span><span class="sxs-lookup"><span data-stu-id="b7f99-151">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="b7f99-152">설치된 .NET Framework 버전: .NET Framework 4 및 COM 구성 요소에서 사용하는 다른 모든 버전의 .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7f99-152">.NET Framework versions installed: The .NET Framework 4 and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="b7f99-153">할 일: 이 시나리오에서는 수행할 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-153">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="b7f99-154">COM 구성 요소는 등록된 .NET Framework 버전과 함께 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-154">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
- <span data-ttu-id="b7f99-155">**시나리오 2**: .NET Framework 2.0 SP1로 빌드된 관리형 애플리케이션은 .NET Framework 2.0에서 실행하는 것을 선호하지만, 버전 2.0이 없을 경우 .NET Framework 4에서 실행하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-155">**Scenario 2**: Managed application built with the .NET Framework 2.0 SP1 that you would prefer to run with the .NET Framework 2.0, but are willing to run on the .NET Framework 4 if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="b7f99-156">설치된 .NET Framework 버전: .NET Framework 및 .NET Framework 4의 이전 버전.</span><span class="sxs-lookup"><span data-stu-id="b7f99-156">.NET Framework versions installed: An earlier version of the .NET Framework and the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="b7f99-157">할 일: 애플리케이션 디렉터리의 [애플리케이션 구성 파일](../configure-apps/index.md)에서 [\<startup> 요소](../configure-apps/file-schema/startup/startup-element.md) 및 [\<supportedRuntime> 요소](../configure-apps/file-schema/startup/supportedruntime-element.md) 집합을 다음과 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-157">What to do: In the [application configuration file](../configure-apps/index.md) in the application directory, use the [\<startup> element](../configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- <span data-ttu-id="b7f99-158">**시나리오 3:** .NET Framework 4에서 실행하려는 이전 버전의 .NET Framework를 사용하여 빌드된 COM 구성 요소를 사용하는 네이티브 애플리케이션.</span><span class="sxs-lookup"><span data-stu-id="b7f99-158">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="b7f99-159">설치된 .NET Framework 버전: .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b7f99-159">.NET Framework versions installed: The .NET Framework 4.</span></span>  
  
     <span data-ttu-id="b7f99-160">할 일: 애플리케이션 디렉터리의 애플리케이션 구성 파일에서 `useLegacyV2RuntimeActivationPolicy` 특성이 `true`로 설정된 `<startup>` 요소 및 `<supportedRuntime>` 요소 집합을 다음과 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-160">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="b7f99-161">예제</span><span class="sxs-lookup"><span data-stu-id="b7f99-161">Example</span></span>  
 <span data-ttu-id="b7f99-162">다음 예제에서는 구성 요소가 사용하도록 컴파일된 .NET Framework 버전을 사용하여 관리되는 COM 구성 요소를 실행하는 관리되지 않는 COM 호스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-162">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="b7f99-163">다음 예제를 실행하려면 .NET Framework 3.5를 사용하여 다음 관리 COM 구성 요소를 컴파일하고 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-163">To run the following example, compile and register the following managed COM component using the .NET Framework 3.5.</span></span> <span data-ttu-id="b7f99-164">구성 요소를 등록하려면 **프로젝트** 메뉴에서 **속성**을 클릭하고 **빌드** 탭을 클릭한 다음 **COM Interop 등록** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-164">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="b7f99-165">앞의 예제에서 만든 COM 개체를 활성화하는 다음과 같은 관리되지 않는 C++ 애플리케이션을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="b7f99-165">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```cpp
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7f99-166">참조</span><span class="sxs-lookup"><span data-stu-id="b7f99-166">See also</span></span>

- [<span data-ttu-id="b7f99-167">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="b7f99-167">\<startup> Element</span></span>](../configure-apps/file-schema/startup/startup-element.md)
- [<span data-ttu-id="b7f99-168">\<supportedRuntime> 요소</span><span class="sxs-lookup"><span data-stu-id="b7f99-168">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
