---
title: BinaryFormatter 보안 가이드
description: 이 문서에서는 BinaryFormatter 형식에 내재된 보안 위험 및 사용할 여러 직렬 변환기에 대한 권장 사항을 설명합니다.
ms.date: 07/11/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 2c76a81650e5b83677f6c4df64770bd1ef5f775e
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88607926"
---
# <a name="binaryformatter-security-guide"></a>BinaryFormatter 보안 가이드

이 문서는 다음과 같은 .NET 구현에 적용됩니다.

* .NET Framework 모든 버전
* .NET Core 2.1 - 3.1
* .NET 5.0 이상

## <a name="background"></a>배경

> [!WARNING]
> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 형식은 위험하므로 데이터 처리에 사용하지 않는 것이 ***좋습니다***. 애플리케이션은 처리 중인 데이터를 신뢰할 수 있다고 생각하는 경우에도 최대한 빨리 `BinaryFormatter` 사용을 중지해야 합니다. `BinaryFormatter`는 안전하지 않으며 안전하게 할 수 없습니다.

이 문서는 다음 형식에도 적용됩니다.

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Web.UI.ObjectStateFormatter>

deserialization 취약성은 요청 페이로드가 안전하지 않게 처리되는 위협 범주입니다. 앱에 대한 deserialization 취약성을 제대로 활용하는 공격자는 대상 앱 내에서 DoS(서비스 거부 공격), 정보 공개 또는 원격 코드 실행을 유발할 수 있습니다. 이 위험 범주는 일관되게 [OWASP 상위 10](https://owasp.org/www-project-top-ten/)에 올랐습니다. 대상으로는 C/C++, Java, C#을 비롯한 [다양한 언어](https://owasp.org/www-community/vulnerabilities/Deserialization_of_untrusted_data)로 작성된 앱이 있습니다.

.NET에서 가장 위험한 대상은 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> 형식을 사용하여 데이터를 역직렬화하는 앱입니다. `BinaryFormatter`는 강력한 기능과 사용 편의성 때문에 .NET 에코시스템 전체에서 널리 사용됩니다. 그러나 이 동일한 기능으로 인해 공격자가 대상 앱 내의 제어 흐름에 영향을 줄 수 있습니다. 공격이 성공하면 공격자가 대상 프로세스의 컨텍스트 내에서 코드를 실행할 수 있습니다.

더 간단한 비유로, 페이로드에 대해 `BinaryFormatter.Deserialize`를 호출하는 것은 해당 페이로드를 독립 실행형 실행 파일로 해석하고 시작하는 것과 같다고 가정합니다.

## <a name="binaryformatter-security-vulnerabilities"></a>BinaryFormatter 보안 취약성

> [!WARNING]
> `BinaryFormatter.Deserialize` 메서드는 신뢰할 수 없는 입력과 함께 사용할 경우 안전하지 __않습니다__. 이 문서의 뒷부분에서 설명하는 대체 방법 중 하나를 대신 사용하는 것이 좋습니다.

`BinaryFormatter`는 deserialization 취약성이 잘 파악된 위협 범주가 되기 전에 구현되었습니다. 따라서 코드가 최신 모범 사례를 따르지 않습니다. `Deserialize` 메서드는 공격자가 앱 사용에 대해 DoS 공격을 수행하기 위한 벡터로 사용될 수 있습니다. 해당 공격으로 인해 앱이 응답하지 않거나 예기치 않게 프로세스가 종료될 수 있습니다. 이 공격 범주는 `SerializationBinder` 또는 다른 `BinaryFormatter` 구성 스위치를 사용하여 완화할 수 없습니다. .NET에서는 이 동작을 ***‘의도적’*** 인 것으로 간주하고 동작을 수정하는 코드 업데이트를 실행하지 않습니다.

`BinaryFormatter.Deserialize`는 정보 공개 또는 원격 코드 실행과 같은 다른 공격 범주에 취약할 수 있습니다. 사용자 지정 <xref:System.Runtime.Serialization.SerializationBinder>와 같은 기능을 활용하는 것만으로는 이러한 위험을 제대로 완화할 수 없습니다. .NET에서 보안 업데이트를 실제로 게시할 수 없는 새로운 취약성이 발견될 가능성이 있습니다. 소비자는 개별 시나리오를 평가하고 이러한 위험에 노출될 가능성을 고려해야 합니다.

`BinaryFormatter` 소비자는 해당 앱에서 개별 위험 평가를 수행하는 것이 좋습니다. `BinaryFormatter`를 활용할지 여부를 결정하는 것은 전적으로 소비자의 책임입니다. 소비자는 `BinaryFormatter` 사용과 관련된 보안, 기술, 평판, 법률 및 규제 요구 사항을 평가하는 위험을 감수해야 합니다.

## <a name="preferred-alternatives"></a>기본 설정 대안

.NET에는 신뢰할 수 없는 데이터를 안전하게 처리할 수 있는 여러 가지 기본 제공 직렬 변환기가 있습니다.

* <xref:System.Xml.Serialization.XmlSerializer> 및 <xref:System.Runtime.Serialization.DataContractSerializer> - 개체 그래프를 XML로 직렬화 및 XML에서 직렬화합니다. `DataContractSerializer`를 <xref:System.Runtime.Serialization.NetDataContractSerializer>와 혼동하지 마세요.
* <xref:System.IO.BinaryReader> 및 <xref:System.IO.BinaryWriter> - XML 및 JSON에 사용됩니다.
* <xref:System.Text.Json> API - 개체 그래프를 JSON으로 직렬화합니다.

## <a name="dangerous-alternatives"></a>위험한 대안

다음 직렬 변환기는 사용하지 마세요.

* <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
* <xref:System.Web.UI.LosFormatter>
* <xref:System.Runtime.Serialization.NetDataContractSerializer>
* <xref:System.Web.UI.ObjectStateFormatter>

앞의 직렬 변환기는 모두 무제한 다형성 deserialization을 수행하며 `BinaryFormatter`와 마찬가지로 위험합니다.

## <a name="the-risks-of-assuming-data-to-be-trustworthy"></a>데이터를 신뢰할 수 있다고 가정할 경우의 위험

앱 개발자가 신뢰할 수 있는 입력만 처리하고 있다고 믿는 경우가 많습니다. 드물긴 하지만 안전한 입력 사례인 경우도 있습니다. 그러나 개발자 모르게 페이로드가 신뢰 경계를 넘어가는 경우가 훨씬 더 일반적입니다.

직원들이 워크스테이션의 데스크톱 클라이언트를 사용하여 서비스를 조작하는 경우 __온-프레미스 서버를 고려합니다__. 이 시나리오는 기본적으로 `BinaryFormatter` 활용이 허용되는 “안전한” 설치로 간주할 수도 있습니다. 그러나 이 시나리오는 단일 직원 머신에 대한 액세스 권한을 얻은 맬웨어가 기업 전체에 확산할 수 있는 벡터를 제공합니다. 해당 맬웨어는 기업의 `BinaryFormatter` 사용을 활용하여 직원 워크스테이션에서 백 엔드 서버로 수평 이동할 수 있습니다. 그런 다음, 회사의 중요한 데이터를 반출할 수 있습니다. 이러한 데이터는 거래 비밀 또는 고객 데이터를 포함할 수 있습니다.

__`BinaryFormatter`를 사용하여 저장 상태를 유지하는 앱도 고려합니다.__ 처음에는 사용자 고유의 하드 드라이브에서 데이터를 읽고 쓰는 것이 사소한 위협을 나타내므로 안전한 시나리오처럼 보일 수 있습니다. 그러나 전자 메일 또는 인터넷을 통한 문서 공유가 일반적이며, 대부분의 최종 사용자는 다운로드된 파일을 여는 것을 위험한 동작으로 인식하지 않습니다.

이 시나리오는 불법적인 결과로 활용될 수 있습니다. 앱이 게임인 경우 저장 파일을 공유하는 사용자는 자신도 모르게 위험에 노출됩니다. 개발자 자신도 대상이 될 수 있습니다. 공격자는 개발자의 기술 지원팀에 전자 메일을 보내고 악성 데이터 파일을 첨부하여 지원 담당자에게 파일을 열도록 요청할 수 있습니다. 이러한 종류의 공격을 통해 공격자는 기업에 침투할 수 있습니다.

또 다른 시나리오는 데이터 파일이 클라우드 스토리지에 저장되고 사용자 머신 간에 자동으로 동기화되는 경우입니다. 클라우드 스토리지 계정에 대한 액세스 권한을 얻을 수 있는 공격자는 데이터 파일을 감염시킬 수 있습니다. 이 데이터 파일이 사용자 머신에 자동으로 동기화됩니다. 사용자가 다음에 데이터 파일을 열면 공격자의 페이로드가 실행됩니다. 따라서 공격자는 클라우드 스토리지 계정 손상을 활용하여 전체 코드 실행 권한을 얻을 수 있습니다.

__데스크톱 설치 모델에서 클라우드 우선 모델로 이동하는 앱을 고려합니다.__ 이 시나리오에는 데스크톱 앱 또는 리치 클라이언트 모델에서 웹 기반 모델로 이동하는 앱이 포함됩니다. 데스크톱 앱에 대해 작성된 모든 위협 모델이 클라우드 기반 서비스에 반드시 적용되는 것은 아닙니다. 데스크톱 앱에 대한 위협 모델에서 지정된 위협을 “자신을 공격하는 클라이언트에 관련이 없는 것”으로 해제할 수도 있습니다. 그러나 클라우드 서비스 자체를 공격하는 원격 사용자(클라이언트)를 고려할 경우 동일한 위협이 관련될 수 있습니다.

> [!NOTE]
> 일반적인 용어의 serialization은 개체를 앱에(서) 전송하기 위한 것입니다. 위협 모델링 연습에서 이러한 종류의 데이터 전송은 거의 항상 신뢰 경계를 넘는 것으로 표시됩니다.

## <a name="further-resources"></a>추가 리소스

* [YSoSerial.Net](https://github.com/pwntester/ysoserial.net) - `BinaryFormatter`를 활용하는 앱을 공격하는 방법 연구
* deserialization 취약성에 대한 일반적인 배경 정보:
  * [OWASP 상위 10 - A8:2017-안전하지 않은 deserialization](https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A8-Insecure_Deserialization)
  * [CWE-502: 신뢰할 수 없는 데이터의 deserialization](https://cwe.mitre.org/data/definitions/502.html)
