---
title: '방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성된 WCF 서비스 호스트'
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: 6a87fd5e3997e9d15810a5efb079da629908f854
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291528"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a><span data-ttu-id="068a5-102">방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성된 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="068a5-102">How to: Host a WCF Service Written with .NET Framework 3.5 in IIS Running Under .NET Framework 4</span></span>
<span data-ttu-id="068a5-103">@No__t-1을 실행 하는 컴퓨터에서 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]으로 작성 된 Windows Communication Foundation (WCF) 서비스를 호스팅하는 경우 다음 텍스트가 포함 된 <xref:System.ServiceModel.ProtocolException>가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-103">When hosting a Windows Communication Foundation (WCF) service written with [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] on a machine running [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], you may get a <xref:System.ServiceModel.ProtocolException> with the following text.</span></span>  
  
```output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 <span data-ttu-id="068a5-104">또는 서비스의 .svc 파일을 찾으려고 하면 다음 텍스트가 포함된 오류 페이지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-104">Or if you try to browse to the service's .svc file you may see an error page with the following text.</span></span>  
  
```output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 <span data-ttu-id="068a5-105">이러한 오류는 IIS가 실행되는 애플리케이션 도메인에서 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]를 실행하고 있지만 WCF 서비스를 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에서 실행해야 하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-105">These errors occur because the application domain IIS is running within is running [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] and the WCF service is expecting to run under [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> <span data-ttu-id="068a5-106">이 항목에서는 서비스가 실행되도록 하는 데 필요한 수정 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-106">This topic explains the modifications required to get the service to run.</span></span>  
  
 <span data-ttu-id="068a5-107">그런 다음 < `compilers` > 요소를 찾고 찾고 compilerversion 공급자 옵션의 값을 4.0로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-107">Next find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="068a5-108">기본적으로 < `compilers` > 요소 아래에는 두 개의 < `compiler` > 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-108">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="068a5-109">다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-109">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
```xml  
<system.codedom>  
      <compilers>  
        <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                  type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
        <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                  type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
          <providerOption name="CompilerVersion" value="v3.5"/>  
          <providerOption name="OptionInfer" value="true"/>  
          <providerOption name="WarnAsError" value="false"/>  
        </compiler>  
      </compilers>  
    </system.codedom>  
```  
  
### <a name="add-the-required-targetframework-attribute"></a><span data-ttu-id="068a5-110">필수 targetFramework 특성 추가</span><span class="sxs-lookup"><span data-stu-id="068a5-110">Add the required targetFramework attribute</span></span>  
  
1. <span data-ttu-id="068a5-111">서비스의 Web.config 파일을 열고 < `compilation` > 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-111">Open the service's Web.config file and look for the <`compilation`> element.</span></span>  
  
2. <span data-ttu-id="068a5-112">다음 예제에 표시 된 것 처럼 < `compilation` > 요소에 `targetFramework` 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-112">Add the `targetFramework` attribute to the <`compilation`> element as shown in the following example.</span></span>  
  
    ```xml  
    <compilation debug="false"  
            targetFramework="4.0">  
  
            <assemblies>  
              <add assembly="System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Xml.Linq, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
              <add assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31BF3856AD364E35"/>  
              <add assembly="System.Data.DataSetExtensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
            </assemblies>  
  
          </compilation>  
    ```  
  
3. <span data-ttu-id="068a5-113">< @No__t-0 > 요소를 찾고 찾고 compilerversion 공급자 옵션의 값을 4.0로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-113">Find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="068a5-114">기본적으로 < `compilers` > 요소 아래에는 두 개의 < `compiler` > 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-114">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="068a5-115">다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="068a5-115">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
    ```xml  
    <system.codedom>  
          <compilers>  
            <compiler language="c#;cs;csharp" extension=".cs" warningLevel="4"  
                      type="Microsoft.CSharp.CSharpCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
            <compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" warningLevel="4"  
                      type="Microsoft.VisualBasic.VBCodeProvider, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
              <providerOption name="CompilerVersion" value="v3.5"/>  
              <providerOption name="OptionInfer" value="true"/>  
              <providerOption name="WarnAsError" value="false"/>  
            </compiler>  
          </compilers>  
        </system.codedom>  
    ```
