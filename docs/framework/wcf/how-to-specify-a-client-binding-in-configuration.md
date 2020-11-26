---
title: '방법: 구성에서 클라이언트 바인딩 지정'
description: 구성 파일에서 WCF 클라이언트에 대 한 바인딩을 선언적으로 지정 하는 방법에 대해 알아봅니다. 클라이언트는이 예제에서 서비스에 액세스 합니다.
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: e8a552211b28c1323b2afd595c5b060db6b2824a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236509"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a>방법: 구성에서 클라이언트 바인딩 지정

이 예제에서는 계산기 서비스를 사용할 클라이언트 콘솔 애플리케이션을 만들고 해당 클라이언트에 대한 바인딩을 구성에 선언적으로 지정합니다. 클라이언트는 `CalculatorService` 인터페이스를 구현하는 `ICalculator`에 액세스하고, 서비스 및 클라이언트 모두 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용합니다.  
  
 설명된 프로시저에서는 계산기 서비스를 실행 중인 것으로 간주합니다. 서비스를 빌드하는 방법에 대 한 자세한 내용은 [방법: 구성에서 서비스 바인딩 지정](how-to-specify-a-service-binding-in-configuration.md)을 참조 하세요. 또한 WCF (Windows Communication Foundation)에서 제공 하는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 클라이언트 구성 요소를 자동으로 생성 합니다. 도구는 서비스 액세스를 위해 클라이언트 코드 및 구성을 생성합니다.  
  
 클라이언트는 두 가지 부분에 빌드됩니다. Svcutil.exe는 `ClientCalculator` 인터페이스를 구현하는 `ICalculator`를 생성합니다. 그런 다음 `ClientCalculator`의 인스턴스를 생성하여 이 클라이언트 애플리케이션을 구성합니다.  
  
 일반적으로 바인딩 및 주소 정보를 코드에서 명령적으로 지정하지 않고 구성에서 선언적으로 지정하는 것이 좋습니다. 일반적으로 배포 된 서비스에 대 한 바인딩 및 주소가 서비스를 개발 하는 동안 사용 된 것과 다르기 때문에 일반적으로 코드에서 끝점을 정의 하는 것은 실용적이 지 않습니다. 일반적으로 바인딩 및 주소 지정 정보를 코드와 구분하면 애플리케이션을 다시 컴파일하거나 다시 배포할 필요 없이 해당 정보를 변경할 수 있습니다.  
  
 [구성 편집기 도구 (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)를 사용 하 여 다음 구성 단계를 모두 수행할 수 있습니다.  
  
 이 예제의 소스 복사에 대해서는 [Basicbinding](./samples/basicbinding.md) 샘플을 참조 하세요.  
  
### <a name="specifying-a-client-binding-in-configuration"></a>구성에서 클라이언트 바인딩 지정  
  
1. 명령줄에서 Svcutil.exe를 사용하여 서비스 메타데이터에서 코드를 생성합니다.  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. 생성된 클라이언트에는 클라이언트 구현에서 충족해야 하는 서비스 계약을 정의하는 `ICalculator` 인터페이스가 포함되어 있습니다.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. 또한 생성된 클라이언트에는 `ClientCalculator`의 구현이 포함되어 있습니다.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. 또한 Svcutil.exe는 <xref:System.ServiceModel.BasicHttpBinding> 클래스를 사용하는 클라이언트의 구성도 생성합니다. Visual Studio를 사용 하는 경우이 파일의 이름을 App.config로 합니다. 주소 및 바인딩 정보는 서비스 구현 내에서 지정 되지 않습니다. 또한 구성 파일에서 해당 정보를 검색하기 위해 코드를 쓰지 않아도 됩니다.  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. 애플리케이션에서 `ClientCalculator`의 인스턴스를 만든 다음 서비스 작업을 호출합니다.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. 클라이언트를 컴파일하고 실행합니다.  
  
## <a name="see-also"></a>참고 항목

- [바인딩을 사용하여 서비스 및 클라이언트 구성](using-bindings-to-configure-services-and-clients.md)
