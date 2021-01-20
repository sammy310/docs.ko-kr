---
title: 최신 데스크톱 응용 프로그램 마이그레이션
description: 최신 데스크톱 응용 프로그램에 대 한 마이그레이션 프로세스에 대해 알아야 하는 모든 것입니다.
ms.date: 01/19/2021
ms.openlocfilehash: b5bea6e601dc040adfd8ed410320a3416cb3372e
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615765"
---
# <a name="migrating-modern-desktop-applications"></a>최신 데스크톱 응용 프로그램 마이그레이션

이 장에서는 기존 응용 프로그램을 .NET Framework에서 .NET으로 마이그레이션할 때 직면 하는 가장 일반적인 문제 및 문제를 살펴보겠습니다.

복잡 한 데스크톱 응용 프로그램은 격리에서 작동 하지 않으며, 로컬 컴퓨터 또는 원격 서버에 상주할 수 있는 하위 시스템에 대 한 일종의 상호 작용이 필요 합니다. 로컬 또는 원격으로 지 속성 저장소로 연결 하는 일종의 데이터베이스가 필요할 수 있습니다. 인터넷 및 서비스 지향 아키텍처의 발생으로 응용 프로그램을 원격 서버 또는 클라우드에 있는 일종의 서비스에 연결 하는 것이 일반적입니다. 일부 기능을 구현 하려면 컴퓨터 파일 시스템에 액세스 해야 할 수 있습니다. 또는 응용 프로그램 외부에 있는 COM 개체 내에 있는 기능을 사용 하는 경우, 예를 들어, 앱에서 Office 어셈블리를 통합 하는 경우 일반적인 시나리오입니다.

뿐만 아니라 .NET Framework 및 .NET에 의해 노출 되는 API 표면의 차이가 있으며 .NET Framework에서 사용할 수 있는 일부 기능은 .NET에서 사용할 수 없습니다. 따라서 마이그레이션을 계획할 때이를 파악 하 고이를 고려 하는 것이 중요 합니다.

## <a name="configuration-files"></a>구성 파일

구성 파일은 런타임에 읽고 응용 프로그램의 동작 (예: 데이터베이스를 찾을 위치 또는 루프를 실행할 횟수)에 영향을 주는 속성 집합을 저장할 수 있는 가능성을 제공 합니다. 이 기술의 장점은 recode 하 고 다시 컴파일하지 않아도 응용 프로그램의 일부 측면을 수정할 수 있다는 것입니다. 예를 들어, 특정 구성 값 집합 및 다른 구성 값을 사용 하는 개발 환경에서 동일한 앱 코드를 실행 하는 경우에 유용 합니다.

### <a name="configuration-on-net-framework"></a>.NET Framework 구성

.NET Framework 데스크톱 응용 프로그램을 사용 하는 경우  <xref:System.Configuration.AppSettingsSection> `System.Configuration` 네임 스페이스에서 클래스를 통해 액세스 하는app.config파일이 있을 수 있습니다.

.NET Framework 인프라 내에서 부모 로부터 속성을 상속 하는 구성 파일의 계층이 있습니다. 모든 하위 구성 파일에서 사용 되거나 재정의 될 수 있는 여러 속성 및 구성 섹션을 정의 하는 *machine.config* 파일을 찾을 수 있습니다.

### <a name="configuration-on-net"></a>.NET의 구성

.NET 환경의 *machine.config* 파일은 없습니다. 이전에 만든 네임 스페이스를 계속 사용할 수 있지만 최신 버전으로 전환 하는 것이 좋습니다 .이를 통해 향상 된 기능을 향상 시킬 수 있습니다 <xref:System.Configuration> <xref:Microsoft.Extensions.Configuration> .

구성 API는 구성을 로드 하는 데 사용할 데이터 원본을 정의 하는 구성 공급자 개념을 지원 합니다. 다음과 같은 다양 한 종류의 기본 제공 공급자가 있습니다.

- 메모리 내 .NET 개체
- INI 파일
- JSON 파일
- XML 파일
- 명령줄 인수
- 환경 변수
- 암호화 된 사용자 저장소

 또는 직접 빌드할 수 있습니다.

새 구성에서는 다중 수준 계층으로 그룹화 할 수 있는 이름-값 쌍 목록을 사용할 수 있습니다. 저장 된 값은 문자열에 매핑되고, 사용자 지정 일반 POCO (CLR object) 개체로 설정을 deserialize 할 수 있는 기본 제공 바인딩 지원이 있습니다.

<xref:Microsoft.Extensions.Configuration.ConfigurationBuilder>개체를 사용 하면 우선 순위를 결정 하는 우선 순위 규칙을 사용 하 여 응용 프로그램에 필요한 수 만큼의 구성 공급자를 추가할 수 있습니다. 따라서 코드에 추가 하는 마지막 공급자는 다른 공급자를 재정의 합니다. 이 기능은 개발, 테스트 및 프로덕션 환경에 대해 서로 다른 구성을 정의 하 고 코드 내의 단일 함수에서 관리할 수 있기 때문에 다양 한 실행 환경을 관리 하는 데 유용한 기능입니다.

### <a name="migrating-configuration-files"></a>구성 파일 마이그레이션

기존 app.config XML 파일을 계속 사용할 수 있습니다. 그러나이 기회를 통해 .NET에서 제공 하는 여러 가지 향상 된 기능을 활용 하 여 구성을 마이그레이션할 수 있습니다.

이전 스타일의 *app.config* 에서 새 구성 파일로 마이그레이션하려면 XML 형식과 JSON 형식 중에서 선택 해야 합니다.

XML을 선택 하면 간단 하 게 변환할 수 있습니다. 내용이 동일 하므로 XML을 사용 하 여 *app.config* 파일을 형식으로 저장 하면 됩니다. 그런 다음 AppSettings를 참조 하는 코드를 클래스를 사용 하도록 변경 합니다 `ConfigurationBuilder` . 이렇게 변경 하는 것이 쉽습니다.

JSON 형식을 사용 하려는 경우 수동으로 마이그레이션하지 않으려는 경우 *app.config* 파일을 json 구성 파일로 변환할 수 있는 [config2json](https://www.nuget.org/packages/dotnet-config2json/) 이라는 도구가 .net에서 제공 됩니다.

*machine.config* 파일에 정의 된 구성 섹션을 사용 하는 경우 몇 가지 문제가 발생할 수도 있습니다. 예를 들어 다음 구성을 고려 하십시오.

```xml
<configuration>
    <system.diagnostics>
        <switches>
            <add name="General" value="4" />
        </switches>
        <trace autoflush="true" indentsize="2">
            <listeners>
                <add name="myListener"
                     type="System.Diagnostics.TextWriterTraceListener,
                           System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
                     initializeData="MyListener.log"
                     traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />
            </listeners>
        </trace>
    </system.diagnostics>
</configuration>
```

이 구성을 .NET으로 사용 하는 경우 다음과 같은 예외가 발생 합니다.

> 인식할 수 없는 구성 섹션 시스템 진단

이 예외는 해당 섹션을 처리 하는 어셈블리와 해당 섹션이 현재 존재 하지 않는 *machine.config* 파일에 정의 되어 있기 때문에 발생 합니다.

문제를 쉽게 해결 하려면 이전 *machine.config* 에서 섹션 정의를 새 구성 파일에 복사 하면 됩니다.

```xml
<configSections>
    <section name="system.diagnostics"
             type="System.Diagnostics.SystemDiagnosticsSection,
                   System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
</configSections>
```

## <a name="accessing-databases"></a>데이터베이스 액세스

거의 모든 데스크톱 응용 프로그램에는 일종의 데이터베이스가 필요 합니다. 데스크톱의 경우 데스크톱 앱과 데이터베이스 엔진 간의 직접 연결을 사용 하 여 클라이언트-서버 아키텍처를 찾는 것이 일반적입니다. 이러한 데이터베이스는 여러 사용자 간에 정보를 공유 해야 하는 필요성에 따라 로컬 또는 원격 일 수 있습니다.

코드 관점에서 개발자에 게 데이터베이스 연결, 쿼리 및 업데이트를 허용 하는 여러 기술 및 프레임 워크가 있습니다.

Windows 데스크톱 응용 프로그램에 대해 이야기할 때 찾을 수 있는 가장 일반적인 데이터베이스 예는 Microsoft Access 및 Microsoft SQL Server입니다. 데스크톱에 대 한 20 년간의 경험을 보유 하 고 있는 경우 ODBC, OLEDB, RDO, ADO, ADO.NET, LINQ 및 Entity Framework 같은 이름이 익숙할 것입니다.

### <a name="odbc"></a>ODBC

Microsoft에서 `System.Data.Odbc` .NET Standard 2.0와 호환 되는 라이브러리를 제공 하므로 .net에서 ODBC를 계속 사용할 수 있습니다.

### <a name="ole-db"></a>OLE DB

[OLE DB](/previous-versions/windows/desktop/ms722784(v=vs.85)) 은 일관 된 방식으로 다양 한 데이터 원본에 액세스할 수 있는 좋은 방법입니다. 그러나이는 Windows 전용 기술인 COM을 기반으로 하며, .NET 등의 플랫폼 간 기술에는 적합 하지 않습니다. SQL Server 버전 2014 이상 에서도 지원 되지 않습니다. 이러한 이유로 .NET에서는 OLE DB 지원 되지 않습니다.

### <a name="adonet"></a>ADO.NET

.NET에서 기존 데스크톱 코드의 ADO.NET를 계속 사용할 수 있습니다. 일부 NuGet 패키지를 업데이트 하기만 하면 됩니다.

### <a name="ef-core-vs-ef6"></a>EF Core와 EF6 비교

현재 지원 되는 Entity Framework (EF), Entity Framework 6 (EF6) 및 EF Core의 두 가지 버전이 있습니다.

.NET Framework 환경의 일부로 출시 된 최신 기술은 Entity Framework 이며 6.4는 최신 버전입니다. Microsoft는 .NET Core를 출시 하 여 Entity Framework 및 Entity Framework Core를 기반으로 새 데이터 액세스 스택을 릴리스 했습니다.

EF 6.4 및 EF Core는 .NET Framework와 .NET 둘 다에서 사용할 수 있습니다. 그렇다면 결정을 내리는 데 도움이 되는 결정 드라이버는 무엇 인가요?

EF 6.3은 .NET에서 실행 되 고 플랫폼 간 작업을 수행할 수 있는 EF6의 첫 번째 버전입니다. 실제로이 릴리스의 주요 목표는 EF6를 사용 하는 기존 응용 프로그램을 .NET으로 쉽게 마이그레이션할 수 있게 하는 것 이었습니다.

EF Core는 EF6와 유사한 개발자 환경을 제공하도록 디자인되었습니다. 대부분의 상위 API가 그대로 유지되므로 EF6를 사용한 개발자에게는 EF Core가 친숙할 것입니다.

호환 되기는 하지만 결정 하기 전에 확인 해야 하는 구현에는 차이점이 있습니다.
자세한 내용은 [Compare EF Core & EF6](/ef/efcore-and-ef6/)를 참조 하세요.

EF Core를 사용 하는 것이 좋습니다.

* 앱은 .NET의 기능을 필요로 합니다.
* EF Core는 앱에 필요한 모든 기능을 지원합니다.

다음 조건이 모두 충족되면 EF6를 사용해 보세요.

* 앱은 Windows 및 .NET Framework 4.0 이상에서 실행 됩니다.
* EF6는 앱에 필요한 모든 기능을 지원합니다.

### <a name="relational-databases"></a>관계형 데이터베이스

#### <a name="sql-server"></a>SQL Server

몇 년 전에 데스크톱을 개발 하는 경우에는 SQL Server가 선택 된 데이터베이스 중 하나 였습니다. .NET Framework에서를 사용 하면 <xref:System.Data.SqlClient> 데이터베이스 관련 프로토콜을 캡슐화 하는 SQL Server 버전에 액세스할 수 있습니다.

.NET에서는 `SqlClient` .NET Framework에 있는 기존 클래스와 완전히 호환 되지만 라이브러리에 있는 새 클래스를 찾을 수 있습니다 <xref:Microsoft.Data.SqlClient> . 단지 [Microsoft. SqlClient](https://www.nuget.org/packages/Microsoft.Data.SqlClient/) NuGet 패키지에 대 한 참조를 추가 하 고 네임 스페이스에 대 한 일부 이름을 지정 해야 하며 모든 것이 예상 대로 작동 해야 합니다.

#### <a name="microsoft-access"></a>Microsoft Access

Microsoft Access는 정교 하 고 확장 가능한 SQL Server 필요 하지 않은 경우 몇 년 동안 사용 되었습니다. 라이브러리를 사용 하 여 Microsoft Access에 계속 연결할 수 있습니다 <xref:System.Data.Odbc> .

## <a name="consuming-services"></a>서비스 사용

서비스 지향 아키텍처의 발생으로 데스크톱 응용 프로그램은 클라이언트-서버 모델에서 3 계층 접근 방식으로 발전 하기 시작 했습니다. 클라이언트-서버 접근 방식에서는 비즈니스 논리를 포함 하는 클라이언트에서 직접 데이터베이스 연결이 설정 됩니다 .이는 일반적으로 단일 EXE 파일 내에 있습니다. 반면 3 계층 접근 방식은 비즈니스 논리 및 데이터베이스 액세스를 구현 하는 중간 서비스 계층을 설정 하 여 더 나은 보안, 확장성 및 재사용을 가능 하 게 합니다. 데이터의 데이터 집합으로 직접 작업 하는 대신 계층 접근 방식은 계약을 구현 하는 서비스 집합과 데이터 전송을 구현 하는 방법으로 개체를 사용 합니다.

WCF 서비스를 사용 하는 데스크톱 응용 프로그램이 있고이를 .NET으로 마이그레이션하려면 몇 가지 사항을 고려해 야 합니다.

첫 번째는 서비스에 액세스 하는 구성을 확인 하는 방법입니다. .NET에서는 구성이 다르므로 구성 파일에서 일부 업데이트를 수행 해야 합니다.

둘째, Visual Studio 2019에 있는 새 도구를 사용 하 여 서비스 클라이언트를 다시 생성 해야 합니다. 이 단계에서는 클라이언트가 기존 코드와 호환 되도록 동기 작업 생성을 활성화 하는 것을 고려해 야 합니다.

마이그레이션 후 .NET에 없는 라이브러리가 필요한 경우에는 [Microsoft. Compatibility](https://www.nuget.org/packages/Microsoft.Windows.Compatibility) NuGet 패키지에 대 한 참조를 추가 하 고 누락 된 함수가 있는지 확인할 수 있습니다.

클래스를 사용 하 여 <xref:System.Net.WebRequest> 웹 서비스 호출을 수행 하는 경우 .net에서 몇 가지 차이점을 확인할 수 있습니다. 대신 시스템 .Net. Http HttpClient를 사용 하는 것이 좋습니다.

## <a name="consuming-a-com-object"></a>COM 개체 사용

현재 .NET과 함께 사용 하기 위해 Visual Studio 2019의 COM 개체에 대 한 참조를 추가할 수 있는 방법은 없습니다. 따라서 프로젝트 파일을 수동으로 수정 해야 합니다.

`COMReference`다음 예제와 같이 프로젝트 파일 내에 구조를 삽입 합니다.

```xml
<ItemGroup>
    <COMReference Include="MSHTML">
        <Guid>{3050F1C5-98B5-11CF-BB82-00AA00BDCE0B}\</Guid>
        <VersionMajor>4</VersionMajor>
        <VersionMinor>0</VersionMinor>
        <Lcid>0</Lcid>
        <WrapperTool>primary</WrapperTool>
        <Isolated>false</Isolated>
    </COMReference>
</ItemGroup>
```

## <a name="more-things-to-consider"></a>고려해 야 할 사항

.NET Framework 라이브러리에서 사용할 수 있는 몇 가지 기술은 .NET Core 또는 .NET 5에서 사용할 수 없습니다. 코드가 이러한 기술 중 일부를 사용 하는 경우이 섹션에 설명 된 대체 방법을 고려 합니다.

[Windows 호환 기능 팩](../../core/porting/windows-compat-pack.md) 은 이전에 .NET Framework에만 사용할 수 있었던 api에 대 한 액세스를 제공 합니다. .NET Core 및 .NET Standard 프로젝트에서 사용할 수 있습니다.

API 호환성에 대 한 자세한 내용은에서 주요 변경 사항 및 사용 되지 않는/레거시 Api에 대 한 설명서를 찾을 수 있습니다 <https://docs.microsoft.com/dotnet/core/compatibility/fx-core> .

### <a name="appdomains"></a>AppDomain

애플리케이션 도메인(AppDomains)은 앱을 서로 분리합니다. Appdomain에는 런타임 지원이 필요 하 고 비용이 많이 듭니다. 추가 앱 도메인 만들기는 지원 되지 않습니다. 코드 격리의 경우 별도의 프로세스 또는 컨테이너를 대신 사용하는 것이 좋습니다. 어셈블리를 동적으로 로드하기 위해 새 <xref:System.Runtime.Loader.AssemblyLoadContext> 클래스를 사용하는 것이 좋습니다.

.NET Framework에서 코드 마이그레이션을 더 쉽게 수행 하기 위해 .NET은 몇 가지 `AppDomain` API 화면을 노출 합니다. API 중 일부는 정상적으로 작동하고(예: <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), 일부 멤버는 아무것도 수행하지 않고(예: <xref:System.AppDomain.SetCachePath%2A>), 일부는 <xref:System.PlatformNotSupportedException>을 throw합니다(예: <xref:System.AppDomain.CreateDomain%2A>).

### <a name="remoting"></a>원격 통신

.NET Remoting은 더 이상 지원 되지 않는 AppDomain 간 통신에 사용 되었습니다. 또한 원격 통신에는 유지 관리 비용이 많이 드는 런타임 지원이 필요합니다. 이러한 이유로 .net Remoting은 .NET에서 지원 되지 않습니다.

프로세스 간 통신의 경우 또는 클래스와 같은 원격 기능 대신 IPC (프로세스 간 통신) 메커니즘을 고려해 야 합니다 <xref:System.IO.Pipes?displayProperty=nameWithType> <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> .

여러 컴퓨터에서 네트워크 기반 솔루션을 대신 사용하세요. HTTP와 같은 오버 헤드가 낮은 일반 텍스트 프로토콜을 사용 하는 것이 좋습니다. ASP.NET Core에서 사용하는 웹 서버인 Kestrel 웹 서버도 옵션이 될 수 있습니다.

### <a name="code-access-security-cas"></a>CAS(코드 액세스 보안)

런타임이나 프레임 워크를 사용 하 여 관리 되는 응용 프로그램 또는 라이브러리가 사용 하거나 실행 하는 리소스를 제한 하는 샌드 박싱은 .NET에서 지원 되지 않습니다.

운영 체제에서 제공 하는 보안 경계 (예: 가상화, 컨테이너 또는 사용자 계정)를 사용 하 여 최소 권한 집합으로 프로세스를 실행 합니다.

### <a name="security-transparency"></a>보안 투명도

CAS와 마찬가지로 보안 투명도는 샌드박스 코드를 보안상 중요한 코드와 선언적인 방식으로 분리할 수 있지만 더 이상 보안 경계로서 지원되지는 않습니다.

최소 권한 집합으로 프로세스를 실행 하기 위해 가상화, 컨테이너 또는 사용자 계정과 같은 운영 체제에서 제공 하는 보안 경계를 사용 합니다.

>[!div class="step-by-step"]
>[이전](whats-new-dotnet.md )
>[다음](windows-migration.md)
