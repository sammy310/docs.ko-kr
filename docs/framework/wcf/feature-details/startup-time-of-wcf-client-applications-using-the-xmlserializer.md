---
title: '방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: b6f010cb5edc3111f05c78f5d27cf178bd501ef9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326426"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>방법: XmlSerializer를 사용하여 WCF 클라이언트 애플리케이션의 시작 시간 향상
<xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize할 수 있는 데이터 형식을 사용하는 서비스 및 클라이언트 응용 프로그램은 런타임에 해당 데이터 형식에 대한 serialization 코드를 생성하고 컴파일합니다. 이로 인해 시작 시 성능이 저하될 수 있습니다.  
  
> [!NOTE]
>  미리 생성된 serialization 코드는 서비스가 아닌 클라이언트 응용 프로그램에서만 사용할 수 있습니다.  
  
 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 응용 프로그램에 대 한 컴파일된 어셈블리 로부터 필요한 serialization 코드를 생성 하 여 이러한 응용 프로그램의 시작 성능을 향상 시킬 수 있습니다. Svcutil.exe는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize될 수 있는 컴파일된 응용 프로그램 어셈블리에서 서비스 계약에 사용하는 모든 데이터 형식에 대한 serialization 코드를 생성합니다. <xref:System.Xml.Serialization.XmlSerializer>를 사용하는 서비스 및 작업 계약은 <xref:System.ServiceModel.XmlSerializerFormatAttribute>와 함께 표시됩니다.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>XmlSerializer serialization 코드를 생성하려면  
  
1. 서비스 또는 클라이언트 코드를 하나 이상의 어셈블리로 컴파일합니다.  
  
2. SDK 명령 프롬프트를 엽니다.  
  
3. 명령 프롬프트에서 다음 형식을 사용하여 Svcutil.exe 도구를 실행합니다.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     `assemblyPath` 인수는 서비스 계약 형식이 포함된 어셈블리의 경로를 지정합니다. Svcutil.exe는 <xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize될 수 있는 컴파일된 응용 프로그램 어셈블리에서 서비스 계약에 사용하는 모든 데이터 형식에 대한 serialization 코드를 생성합니다.  
  
     Svcutil.exe는 C# serialization 코드만 생성할 수 있습니다. 각 입력 어셈블리에 대해서 하나의 소스 코드 파일이 생성됩니다. 사용할 수 없습니다는 **/language** 스위치 생성된 된 코드의 언어를 변경 합니다.  
  
     종속 어셈블리의 경로를 지정 하려면 사용 합니다 **/reference** 옵션입니다.  
  
4. 다음 옵션 중 하나를 사용하여 생성된 serialization 코드를 응용 프로그램에서 사용할 수 있도록 합니다.  
  
    1.  이름 사용 하 여 별도 어셈블리로 생성된 된 serialization 코드를 컴파일 [*원래 어셈블리*]. .Xmlserializers.dll (예: MyApp.XmlSerializers.dll)입니다. 응용 프로그램에서 어셈블리를 로드할 수 있어야 하며, 해당 어셈블리는 원본 어셈블리와 동일한 키로 서명되어야 합니다. 원본 어셈블리를 다시 컴파일하면 serialization 어셈블리도 다시 생성해야 합니다.  
  
    2.  생성된 serialization 코드를 별도의 어셈블리로 컴파일하고 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute>를 사용하는 서비스 계약에 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 사용합니다. 컴파일된 serialization 어셈블리를 가리키기 위해 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 또는 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 속성을 설정합니다.  
  
    3.  생성된 serialization 코드를 응용 프로그램 어셈블리로 컴파일하고 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute>를 사용하는 서비스 계약에 <xref:System.ServiceModel.XmlSerializerFormatAttribute>를 추가합니다. <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 또는 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 속성은 설정하지 마십시오. 기본 serialization 어셈블리가 현재 어셈블리로 간주됩니다.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Visual Studio에서 XmlSerializer serialization 코드를 생성 하려면  
  
1. WCF 서비스와 클라이언트 프로젝트 Visual Studio에서 만들기. 그런 다음 클라이언트 프로젝트에 대 한 서비스 참조를 추가 합니다.  
  
2. 추가 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 서비스 계약에 *reference.cs* 아래에 있는 클라이언트 앱 프로젝트에서 파일 **serviceReference** -> **reference.svcmap** . 에 모든 파일 표시 해야 **솔루션 탐색기** 이러한 파일을 볼 수 있습니다.  
  
3. 클라이언트 앱을 빌드하십시오.  
  
4. 사용 된 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 미리 생성 된 serializer를 만들려면 *.cs* 명령을 사용 하 여 파일:  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     AssemblyPath 인수에는 WCF 클라이언트 어셈블리의 경로를 지정합니다.  
  
     와 같은:  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     합니다 *WCFClient.XmlSerializers.dll.cs* 파일이 생성 됩니다.  
  
5. 미리 생성 된 serialization 어셈블리를 컴파일하십시오.  
  
     이전 단계에서 예제에 따라 컴파일 명령은 다음과 같습니다.  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     했는지 생성 된 *WCFClient.XmlSerializers.dll* 는 클라이언트 앱의 경우와 동일한 디렉터리에 *WCFClient.exe* 이 경우.  
  
6. 클라이언트 앱을 정상적으로 실행 합니다. 미리 생성된 된 serialization 어셈블리 사용 됩니다.  
  
## <a name="example"></a>예제  
 다음 명령은 어셈블리의 모든 서비스 계약이 사용하는 `XmlSerializer` 형식에 대해 serialization 형식을 생성합니다.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>참고자료

- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
