---
title: 워크플로 보안
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: 2a9b26f8da7616480f69a6c4580b8d351833c9ee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646313"
---
# <a name="workflow-security"></a>워크플로 보안
WF(Windows 워크플로우 파운데이션)는 Microsoft SQL Server 및 WCF(Windows 통신 재단)와 같은 여러 가지 기술과 통합되어 있습니다. 이러한 기술과 잘못 상호 작용하면 워크플로에 보안 문제가 발생할 수 있습니다.

## <a name="persistence-security-concerns"></a>지속성 보안 고려 사항

1. <xref:System.Activities.Statements.Delay> 활동 및 지속성을 사용하는 워크플로는 서비스로 다시 활성화해야 합니다. Windows AppFabric은 WMS(워크플로 관리 서비스)를 사용하여 만료된 타이머로 워크플로를 다시 활성화합니다. WMS는 <xref:System.ServiceModel.WorkflowServiceHost>를 만들어 다시 활성화된 워크플로를 호스트합니다. WMS 서비스가 중지된 경우 타이머가 만료되면 지속된 워크플로는 다시 활성화되지 않습니다.

2. 지속적인 인스턴스에 대한 액세스는 애플리케이션 도메인 외부의 악의적인 엔터티로부터 보호되어야 합니다. 또한 지속적인 인스턴스 코드와 같은 애플리케이션 도메인에서 개발자는 악의적인 코드를 실행할 수 없는지 확인해야 합니다.

3. 지속적인 인스턴스는 높은(관리자) 권한으로 실행해서는 안 됩니다.

4. 애플리케이션 도메인 외부에서 처리되는 데이터는 보호해야 합니다.

5. 보안 격리가 필요한 애플리케이션은 스키마 추상화의 같은 인스턴스를 공유해서는 안 됩니다. 이런 애플리케이션은 다른 스토리지 공급자 또는 다른 스토리지 인스턴스를 사용하도록 구성된 스토리지 공급자를 사용해야 합니다.

## <a name="sql-server-security-concerns"></a>SQL Server 보안 고려 사항

- 많은 수의 자식 활동, 위치, 책갈피, 호스트 확장 또는 범위를 사용하거나 매우 큰 페이로드가 있는 책갈피를 사용할 때는 메모리가 부족하거나 유지 중에 과도한 양의 데이터베이스 공간이 할당될 수 있습니다. 개체 수준 및 데이터베이스 수준 보안을 사용하여 이 문제를 완화할 수 있습니다.

- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 사용할 때는 인스턴스 저장소를 보호해야 합니다.

- 인스턴스 저장소의 중요 데이터를 암호화해야 합니다. 자세한 내용은 [SQL Server Encryption](/sql/relational-databases/security/encryption/sql-server-encryption)를 참조하세요.

- 데이터베이스 연결 문자열은 종종 구성 파일에 포함되기 때문에 Windows 수준 보안(ACL)을 사용하여 구성 파일(대개 Web.Config)이 안전한지, 로그인과 암호 정보가 연결 문자열에 포함되어 있지 않은지 확인해야 합니다. 대신 데이터베이스와 웹 서버 사이에는 Windows 인증을 사용해야 합니다.

## <a name="considerations-for-workflowservicehost"></a>WorkflowServiceHost에 대한 고려 사항

- 워크플로에 사용되는 WCF(Windows 통신 재단) 끝점을 보호해야 합니다. 자세한 내용은 [WCF 보안 개요를](../wcf/feature-details/security-overview.md)참조하십시오.

- <xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 호스트 수준 권한 부여를 구현할 수 있습니다. [방법: 서비스에 대한 사용자 지정 권한 부여 관리자 를 만들어](../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md) 자세한 내용을 확인하세요.

- 들어오는 메시지에 대한 ServiceSecurityContext는 OperationContext에 액세스하여 워크플로 내에서도 사용할 수 있습니다.

## <a name="wf-security-pack-ctp"></a>WF Security Pack CTP
 Microsoft WF 보안 팩 커뮤니티 기술 미리 보기(CTP) 1은 [.NET Framework 4(WF 4)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0x726c2(v=vs.100)) 및 [Windows ID Foundation(WIF)의](https://docs.microsoft.com/previous-versions/dotnet/framework/security/index) [Windows 워크플로 우영 재단을](index.md) 기반으로 한 일련의 활동 및 구현입니다. Microsoft WF Security Pack CTP 1에는 다음과 같은 워크플로를 사용하여 다양한 보안 관련 시나리오를 손쉽게 사용하는 방법을 보여 주는 활동과 디자이너가 모두 포함되어 있습니다.

1. 워크플로에서 클라이언트 ID 가장

2. PrincipalPermission 및 클레임의 유효성 검사 같은 워크플로 내 인증

3. 사용자 이름/암호 또는 STS(보안 토큰 서비스)에서 검색한 토큰 같은 워크플로에 지정된 ClientCredentials을 사용하여 인증된 메시징

4. WS-Trust ActAs를 사용하여 클라이언트 보안 토큰이 백엔드 서비스로 이동(클레임 기반 위임)

WF 보안 팩 CTP를 다운로드하려면 [WF 보안 팩 CTP를](https://archive.codeplex.com/?p=wf) 참조하십시오.
