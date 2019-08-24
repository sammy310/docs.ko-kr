---
title: '방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성된 WCF 서비스 호스트'
ms.date: 03/30/2017
ms.assetid: 9aabc785-068d-4d32-8841-3ef39308d8d6
ms.openlocfilehash: eb4f0538380bf2e1d0e36d69020787055230dbaf
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425570"
---
# <a name="how-to-host-a-wcf-service-written-with-net-framework-35-in-iis-running-under-net-framework-4"></a>방법: .NET Framework 4에서 실행되는 IIS에서 .NET Framework 3.5를 사용하여 작성된 WCF 서비스 호스트
로 작성 된 Windows Communication Foundation (WCF) 서비스를 호스트할 때 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)] 실행 하는 컴퓨터에 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], 표시 될 수 있습니다는 <xref:System.ServiceModel.ProtocolException> 다음 텍스트를 포함 합니다.  
  
```Output  
Unhandled Exception: System.ServiceModel.ProtocolException: The content type text/html; charset=utf-8 of the response message does not match the content type of the binding (application/soap+xml; charset=utf-8). If using a custom encoder, be sure that the IsContentTypeSupported method is implemented properly. The first 1024 bytes of the response were: '<html>    <head>        <title>The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.</title>...  
```  
  
 또는 서비스의 .svc 파일을 찾으려고 하면 다음 텍스트가 포함된 오류 페이지가 표시될 수 있습니다.  
  
```Output  
The application domain or application pool is currently running version 4.0 or later of the .NET Framework. This can occur if IIS settings have been set to 4.0 or later for this Web application, or if you are using version 4.0 or later of the ASP.NET Web Development Server. The <compilation> element in the Web.config file for this Web application does not contain the required 'targetFrameworkMoniker' attribute for this version of the .NET Framework (for example, '<compilation targetFrameworkMoniker=".NETFramework,Version=v4.0">'). Update the Web.config file with this attribute, or configure the Web application to use a different version of the .NET Framework.  
```  
  
 이러한 오류는 IIS가 실행되는 애플리케이션 도메인에서 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]를 실행하고 있지만 WCF 서비스를 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에서 실행해야 하는 경우 발생합니다. 이 항목에서는 서비스가 실행되도록 하는 데 필요한 수정 작업에 대해 설명합니다.  
  
 다음 찾기는 <`compilers`> 요소 및 4.0 값 CompilerVersion 공급자 옵션 변경 합니다. 기본적으로 두 개의 <`compiler`> 요소는 <`compilers`> 요소입니다. 다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.  
  
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
  
### <a name="add-the-required-targetframework-attribute"></a>필수 targetFramework 특성 추가  
  
1. 서비스의 Web.config 파일을 열고 검색할 합니다 <`compilation`> 요소입니다.  
  
2. 추가 된 `targetFramework` 특성을 <`compilation`> 다음 예제에서와 같이 요소입니다.  
  
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
  
3. 찾을 합니다 <`compilers`> 요소 및 4.0 값 CompilerVersion 공급자 옵션 변경 합니다. 기본적으로 두 개의 <`compiler`> 요소는 <`compilers`> 요소입니다. 다음 예제와 같이 이 두 요소 모두에 대해 CompilerVersion 공급자 옵션을 업데이트해야 합니다.  
  
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
