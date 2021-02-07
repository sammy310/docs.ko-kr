---
description: '자세한 정보: 방법: .NET Framework 4에서 실행 되는 IIS에서 .NET Framework 3.5으로 작성 된 WCF 서비스 호스팅'
title: '방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성된 WCF 서비스 호스트'
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: 3ea46b589df293b39369521a133cf9facad97d93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755969"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a><span data-ttu-id="4c409-103">방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성된 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="4c409-103">How to: Host a WCF Service Written with .NET Framework 3.5 in IIS Running Under .NET Framework 4</span></span>

<span data-ttu-id="4c409-104">.NET Framework 4를 실행 하는 컴퓨터에서 .NET Framework 3.5를 사용 하 여 작성 된 WCF (Windows Communication Foundation) 서비스를 호스팅하는 경우 다음 텍스트가 표시 될 수 있습니다 <xref:System.ServiceModel.ProtocolException> .</span><span class="sxs-lookup"><span data-stu-id="4c409-104">When hosting a Windows Communication Foundation (WCF) service written with .NET Framework 3.5 on a machine running .NET Framework 4, you may get a <xref:System.ServiceModel.ProtocolException> with the following text.</span></span>
  
```output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 <span data-ttu-id="4c409-105">또는 서비스의 .svc 파일을 찾으려고 하면 다음 텍스트가 포함된 오류 페이지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-105">Or if you try to browse to the service's .svc file you may see an error page with the following text.</span></span>  
  
```output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 <span data-ttu-id="4c409-106">이러한 오류는 IIS에서 실행 되는 응용 프로그램 도메인의 .NET Framework 4가 실행 중이 고 WCF 서비스가 .NET Framework 3.5에서 실행 될 것으로 예상 되기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-106">These errors occur because the application domain IIS is running within is running .NET Framework 4 and the WCF service is expecting to run under .NET Framework 3.5.</span></span> <span data-ttu-id="4c409-107">이 항목에서는 서비스가 실행되도록 하는 데 필요한 수정 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-107">This topic explains the modifications required to get the service to run.</span></span>
  
 <span data-ttu-id="4c409-108">그런 다음 <`compilers`> 요소를 찾고 찾고 compilerversion 공급자 옵션의 값을 4.0로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-108">Next find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="4c409-109">기본적으로 `compiler` <> 요소 아래에는 두 개의 <> 요소가 있습니다 `compilers` .</span><span class="sxs-lookup"><span data-stu-id="4c409-109">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="4c409-110">다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-110">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
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
  
### <a name="add-the-required-targetframework-attribute"></a><span data-ttu-id="4c409-111">필수 targetFramework 특성 추가</span><span class="sxs-lookup"><span data-stu-id="4c409-111">Add the required targetFramework attribute</span></span>  
  
1. <span data-ttu-id="4c409-112">서비스의 Web.config 파일을 열고 <> 요소를 찾습니다 `compilation` .</span><span class="sxs-lookup"><span data-stu-id="4c409-112">Open the service's Web.config file and look for the <`compilation`> element.</span></span>  
  
2. <span data-ttu-id="4c409-113">`targetFramework`다음 예제와 같이 특성을 <> 요소에 추가 합니다 `compilation` .</span><span class="sxs-lookup"><span data-stu-id="4c409-113">Add the `targetFramework` attribute to the <`compilation`> element as shown in the following example.</span></span>  
  
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
  
3. <span data-ttu-id="4c409-114"><`compilers`> 요소를 찾고 찾고 compilerversion 공급자 옵션의 값을 4.0로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-114">Find the <`compilers`> element and change the CompilerVersion provider option to have a value of 4.0.</span></span> <span data-ttu-id="4c409-115">기본적으로 `compiler` <> 요소 아래에는 두 개의 <> 요소가 있습니다 `compilers` .</span><span class="sxs-lookup"><span data-stu-id="4c409-115">By default, there are two <`compiler`> elements under the <`compilers`> element.</span></span> <span data-ttu-id="4c409-116">다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c409-116">You must update the CompilerVersion provider option for both as shown in the following example.</span></span>  
  
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
