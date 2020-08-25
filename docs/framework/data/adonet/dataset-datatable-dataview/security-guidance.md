---
title: DataSet 및 DataTable 보안 지침
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: 24c8a830f8638bc2d9dd20c2384c8230a682d817
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812239"
---
# <a name="dataset-and-datatable-security-guidance"></a>DataSet 및 DataTable 보안 지침

이 문서는 다음에 적용 됩니다.

* .NET Framework(모든 버전)
* .NET Core 이상
* .NET 5.0 이상

[DataSet](/dotnet/api/system.data.dataset) 및 [DataTable](/dotnet/api/system.data.datatable) 형식은 데이터 집합을 관리 되는 개체로 표현할 수 있도록 하는 레거시 .net 구성 요소입니다. 이러한 구성 요소는 원래 [ADO.NET 인프라](/dotnet/framework/data/adonet/dataset-datatable-dataview/)의 일부로 .net 1.0에서 도입 되었습니다. 이러한 목표는 관계형 데이터 집합에 대 한 관리 되는 뷰를 제공 하 여 데이터의 기본 원본이 XML, SQL 또는 다른 기술 인지 여부를 추상화 하는 것 이었습니다.

최신 데이터 뷰 패러다임을 비롯 한 ADO.NET에 대 한 자세한 내용은 [ADO.NET 설명서](/dotnet/framework/data/adonet/)를 참조 하세요.

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a>XML에서 DataSet 또는 DataTable을 deserialize 할 때의 기본 제한 사항

지원 되는 모든 버전의 .NET Framework, .NET Core 및 .NET에서 `DataSet` `DataTable` deserialize 된 데이터에 표시 될 수 있는 개체 형식에 대해 다음과 같은 제한 사항을 적용 합니다. 기본적으로이 목록은 다음으로 제한 됩니다.

* 기본 형식 및 해당 하는 기본 형식:,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,, `bool` `char` `sbyte` `byte` `short` `ushort` `int` `uint` `long` `ulong` `float` `double` `decimal` `DateTime` `DateTimeOffset` `TimeSpan` `string` `Guid` `SqlBinary` `SqlBoolean` `SqlByte` `SqlBytes` `SqlChars` `SqlDateTime` `SqlDecimal` `SqlDouble` `SqlGuid` `SqlInt16` `SqlInt32` `SqlInt64` `SqlMoney` `SqlSingle` 및 `SqlString`
* 일반적으로 사용 되는 기본 형식이 아닌 `Type` , `Uri` 및 `BigInteger` 입니다.
* 일반적으로 사용 되는 _system.web_ ,,,,, `Color` `Point` `PointF` `Rectangle` `RectangleF` `Size` 및 `SizeF` 입니다.
* `Enum` 종류.
* 위 형식의 배열 및 목록입니다.

들어오는 XML 데이터에이 목록에 없는 형식의 개체가 포함 된 경우:

* 다음 메시지 및 스택 추적을 사용 하 여 예외가 throw 됩니다.  
오류 메시지:  
InvalidOperationException: Type ' \<Type Name\> , Version = \<n.n.n.n\> , Culture = \<culture\> , PublicKeyToken = \<token value\> '는 여기에서 사용할 수 없습니다. [https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227)자세한 내용은을 참조 하세요.  
스택 추적:  
at TypeLimiter. EnsureTypeIsAllowed (Type type, TypeLimiter capturedLimiter)  
at UpdateColumnType (형식 형식, StorageType typeCode)  
at System.web. set_DataType (유형 값)  

* Deserialization 작업이 실패 합니다.

XML `DataSet` 을 기존 또는 인스턴스로 로드할 때 `DataTable` 기존 열 정의도 고려 됩니다. 테이블에 사용자 지정 형식의 열 정의가 이미 포함 되어 있으면 해당 형식이 XML deserialization 작업 기간 동안 허용 목록에 일시적으로 추가 됩니다.

```cs
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

를 사용 하 여 `XmlSerializer` 또는의 인스턴스를 deserialize 하는 경우에도 개체 형식 제한이 적용 됩니다 `DataSet` `DataTable` . 그러나를 사용 하 여 `BinaryFormatter` 또는의 인스턴스를 deserialize 하는 경우에는 적용 되지 않을 수 있습니다 `DataSet` `DataTable` .

를 사용 하는 경우 ( `DataAdapter.Fill` 예: `DataTable` XML deserialization api를 사용 하지 않고 인스턴스를 데이터베이스에서 직접 채우는 경우)에는 개체 유형 제한이 적용 되지 않습니다.

### <a name="extend-the-list-of-allowed-types"></a>허용 되는 형식 목록 확장

앱은 위에 나열 된 기본 제공 유형 외에도 사용자 지정 유형을 포함 하도록 허용 된 유형 목록을 확장할 수 있습니다. 허용 되는 유형 목록을 확장 하면 변경 내용이 _all_ `DataSet` 앱 내의 모든 및 인스턴스에 영향을 줍니다 `DataTable` . 형식은 기본 제공 허용 형식 목록에서 제거할 수 없습니다.

#### <a name="extend-through-configuration-net-framework-40---48"></a>구성을 통해 확장 (.NET Framework 4.0-4.8)

_App.config_ 를 사용 하 여 허용 되는 형식 목록을 확장할 수 있습니다. 허용 되는 유형 목록을 확장 하려면 다음을 수행 합니다.

* 요소를 사용 `<configSections>` 하 여 _system.web_ 구성 섹션에 대 한 참조를 추가 합니다.
* `<system.data.dataset.serialization>` / `<allowedTypes>` 를 사용 하 여 추가 유형을 지정 합니다.

각 `<add>` 요소는 해당 어셈블리의 정규화 된 형식 이름을 사용 하 여 하나의 형식만 지정 해야 합니다. 허용 되는 형식 목록에 다른 형식을 추가 하려면 여러 요소를 사용 `<add>` 합니다.

다음 샘플에서는 사용자 지정 형식을 추가 하 여 허용 되는 형식 목록을 확장 하는 방법을 보여 줍니다 `Fabrikam.CustomType` .

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

형식의 어셈블리 정규화 된 이름을 검색 하려면 다음 코드에 나와 있는 것 처럼 [AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) 속성을 사용 합니다.

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a>구성을 통해 확장 (.NET Framework 2.0-3.5)

앱이 2.0 또는 3.5 .NET Framework를 대상으로 하는 경우에도 위의 _App.config_ 메커니즘을 사용 하 여 허용 되는 유형 목록을 확장할 수 있습니다. 그러나 `<configSections>` 다음 코드와 같이 요소는 약간 다르게 보입니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a>프로그래밍 방식으로 확장 (.NET Framework, .NET Core, .NET 5.0 이상)

다음 코드에 표시 된 것 처럼 잘 _알려진 키를_사용 하는 경우에는 [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) 를 사용 하 여 허용 되는 형식 목록을 프로그래밍 방식으로 확장할 수도 있습니다.

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

확장 메커니즘을 사용 하는 경우에는 key _system.object_ 와 연결 된 값 `Type[]` 이 형식 이어야 합니다.

.NET Framework에서 허용 되는 형식 목록은 _App.config_ 및를 사용 하 여 확장할 수 있습니다 `AppDomain.SetData` . 이 경우 `DataSet` 및 `DataTable` 는 해당 형식이 두 목록에 모두 있는 경우 데이터의 일부로 개체를 deserialize 할 수 있습니다.

### <a name="run-an-app-in-audit-mode-net-framework"></a>감사 모드에서 앱 실행 (.NET Framework)

.NET Framework에서 `DataSet` 및 `DataTable` 는 감사 모드 기능을 제공 합니다. 감사 모드를 사용 하는 `DataSet` 경우 `DataTable` 들어오는 개체의 형식을 허용 되는 형식 목록과 비교 합니다. 그러나 형식이 허용 되지 않는 개체를 볼 수 있는 경우에는 예외가 throw **되지** 않습니다. 대신, `DataSet` 및 `DataTable` `TraceListener` 의심 스러운 형식이 존재 하는 연결 된 인스턴스를 모두 알리고에서 `TraceListener` 이 정보를 기록할 수 있도록 합니다. 예외가 throw 되지 않고 deserialization 작업이 계속 됩니다.

> [!WARNING]
> "감사 모드"에서 응용 프로그램을 실행 하는 것은 테스트에 사용 되는 임시 측정값이 되어야 합니다. 감사 모드를 사용 하도록 설정 하 `DataSet` 고 `DataTable` 형식 제한을 적용 하지 않습니다 .이 경우 앱 내부에 보안 허점이 발생할 수 있습니다. 자세한 내용은 [신뢰할 수 없는 입력과 관련 하 여](#swr) [모든 형식 제한](#ratr) 및 안전 제거 섹션을 참조 하세요.

_App.config_를 통해 감사 모드를 사용 하도록 설정할 수 있습니다.

* 요소에 대 한 적절 한 값에 대 한 자세한 내용은이 문서의 [구성으로 확장](#etc) 섹션을 참조 하세요 `<configSections>` .
* `<allowedTypes auditOnly="true">`다음 태그와 같이를 사용 하 여 감사 모드를 사용 하도록 설정 합니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

감사 모드를 사용 하는 경우 _App.config_ 를 사용 하 여 기본 제공 `TraceListener` `DataSet` `TraceSource.` 추적 소스의 _System.Data.DataSet_이름을 system.string으로 기본 제공 합니다. 다음 샘플에서는 콘솔 _및_ 디스크의 로그 파일에 추적 이벤트를 쓰는 방법을 보여 줍니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

및에 대 한 자세한 내용은 `TraceSource` `TraceListener` [방법: 추적 수신기와 함께 TraceSource 및 필터 사용](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md)문서를 참조 하세요.

> [!NOTE]
> 감사 모드에서 응용 프로그램을 실행 하는 것은 .NET Core 또는 .NET 5.0 이상에서 사용할 수 없습니다.

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a>모든 형식 제한 제거

앱이 및에서 모든 형식 제한 제한을 제거 해야 `DataSet` 하는 경우 `DataTable` 다음을 수행 합니다.

* 형식 제한 제한을 표시 하지 않는 몇 가지 옵션이 있습니다.
* 사용할 수 있는 옵션은 앱이 대상으로 하는 프레임 워크에 따라 다릅니다.

> [!WARNING]
> 모든 형식 제한을 제거 하면 앱 내에 보안 허점이 발생할 수 있습니다. 이 메커니즘을 사용 하는 경우 앱에서 **not** `DataSet` 또는를 사용 `DataTable` 하 여 신뢰할 수 없는 입력을 읽지 않도록 합니다. 자세한 내용은 [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) 및 [신뢰할 수 없는 입력과 관련 하 여](#swr)다음 섹션의 안전성을 참조 하십시오.

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a>AppContext 구성 (.NET Framework 4.6-4.8, .NET Core 2.1 이상, .NET 5.0 이상)을 통해

`AppContext`스위치를 `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` 로 설정 하면 `true` 및에서 모든 형식 제한 제한이 제거 됩니다 `DataSet` `DataTable` .

.NET Framework에서 다음 구성에 표시 된 것 처럼 _App.config_를 통해이 스위치를 사용 하도록 설정할 수 있습니다.

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

ASP.NET에서는 요소를 `<AppContextSwitchOverrides>` 사용할 수 없습니다. 대신 다음 구성에 표시 된 것 처럼 _Web.config_를 통해 스위치를 사용 하도록 설정할 수 있습니다.

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

자세한 내용은 요소를 참조 하세요 [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) .

.NET Core, .NET 5 및 ASP.NET Core에서이 설정은 다음 JSON에 표시 된 것 처럼 _runtimeconfig.js에_의해 제어 됩니다.

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

자세한 내용은 [".Net Core 런타임 구성 설정"](/dotnet/core/run-time-config/)을 참조 하십시오.

`AllowArbitraryDataSetTypeInstantiation` 는 다음 코드와 같이 구성 파일을 사용 하는 대신 [Appcontext. SetSwitch](/dotnet/api/system.appcontext.setswitch) 를 통해 프로그래밍 방식으로 설정할 수도 있습니다.

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 위의 프로그래밍 방식을 선택 하는 경우에 대 한 호출은 `AppContext.SetSwitch` 앱 시작 초기에 발생 해야 합니다.

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a>시스템 수준 레지스트리를 통해 (.NET Framework 2.0-4.8)

`AppContext`을 사용할 수 없는 경우 Windows 레지스트리를 사용 하 여 형식 제한 검사를 사용 하지 않도록 설정할 수 있습니다.

* 관리자가 레지스트리를 구성 해야 합니다.
* 레지스트리를 사용 하는 것은 시스템 전체에서 변경 되며 컴퓨터에서 실행 되는 _모든_ 앱에 영향을 줍니다.

| 형식  |  값 |
|---|---|
| **레지스트리 키** | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| **값 이름** | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| **값 유형** | `REG_SZ` |
| **값 데이터** | `true` |

64 비트 운영 체제에서이 값은 64 비트 키 (위에 표시 됨) 및 32 비트 키 모두에 대해 추가 해야 합니다. 32 비트 키는에 `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` 있습니다.

를 구성 하는 데 레지스트리를 사용 하는 방법에 대 한 자세한 내용은 `AppContext` ["라이브러리 소비자를 위한 appcontext"](/dotnet/api/system.appcontext#appcontext-for-library-consumers)를 참조 하십시오.

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a>신뢰할 수 없는 입력과 관련 된 안전

`DataSet`및는 `DataTable` XML 페이로드를 deserialize 하는 동안 나타날 수 있는 형식에 대 한 기본 제한 사항을 적용 하며, 신뢰할 수 없는 __ `DataSet` `DataTable` 입력으로 채워질 때 일반적으로 안전 하지 않습니다.__ 다음은 `DataSet` 또는 `DataTable` 인스턴스가 신뢰할 수 없는 입력을 읽을 수 있는 방법에 대 한 완전 하지 않은 목록입니다.

* 는 `DataAdapter` 데이터베이스를 참조 하 고 `DataAdapter.Fill` 메서드는를 `DataSet` 데이터베이스 쿼리의 내용으로 채우는 데 사용 됩니다.
* `DataSet.ReadXml`또는 `DataTable.ReadXml` 메서드는 열 및 행 정보를 포함 하는 XML 파일을 읽는 데 사용 됩니다.
* `DataSet`또는 `DataTable` 인스턴스는 ASP.NET (SOAP) 웹 서비스 또는 WCF 끝점의 일부로 serialize 됩니다.
* 와 같은 serializer는 `XmlSerializer` `DataSet` XML 스트림에서 또는 인스턴스를 deserialize 하는 데 사용 됩니다 `DataTable` .
* 와 같은 serializer는 `JsonConvert` `DataSet` JSON 스트림에서 또는 인스턴스를 deserialize 하는 데 사용 됩니다 `DataTable` . `JsonConvert` 는 라이브러리의 인기 있는 타사 [Newtonsoft.Js](https://www.newtonsoft.com/json) 의 메서드입니다.
* 와 같은 serializer는 `BinaryFormatter` `DataSet` 원시 바이트 스트림에서 또는 인스턴스를 deserialize 하는 데 사용 됩니다 `DataTable` .

이 문서에서는 위의 시나리오에 대 한 안전 고려 사항을 설명 합니다.

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a>를 사용 `DataAdapter.Fill` 하 여 `DataSet` 신뢰할 수 없는 데이터 소스에서를 채웁니다.

`DataSet` `DataAdapter` 다음 예제와 같이 [ `DataAdapter.Fill` 메서드](/dotnet/api/system.data.common.dataadapter.fill)를 사용 하 여에서 인스턴스를 채울 수 있습니다.

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

위의 코드 샘플은 [DataAdapter에서 데이터 집합을 채울](../populating-a-dataset-from-a-dataadapter.md)때 발견 되는 더 큰 샘플의 일부입니다.

> 대부분의 앱은 데이터베이스 계층이 신뢰 되는 것으로 단순화 하 고 가정할 수 있습니다. 그러나 앱을 [모델링](https://www.microsoft.com/securityengineering/sdl/threatmodeling) 하는 것이 습관 인 경우 위협 모델은 응용 프로그램 (클라이언트)과 데이터베이스 계층 (서버) 간에 트러스트 경계가 될 것으로 간주할 수 있습니다. 클라이언트와 서버 간의 [상호 인증](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) 또는 [AAD 인증](/azure/azure-sql/database/authentication-aad-overview) 을 사용 하는 것은이와 관련 된 위험을 해결 하는 한 가지 방법입니다. 이 섹션의 나머지 부분에서는 신뢰할 수 없는 서버에 연결 하는 클라이언트의 가능한 결과에 대해 설명 합니다.

`DataAdapter`신뢰할 수 없는 데이터 소스에서를 가리키는 경우의 결과는 자체의 구현에 따라 달라 집니다 `DataAdapter` .

### <a name="sqldataadapter"></a>SqlDataAdapter

기본 제공 형식 [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter)의 경우 신뢰할 수 없는 데이터 원본을 참조 하면 dos (서비스 거부) 공격이 발생할 수 있습니다. DoS 공격으로 인해 앱이 응답 하지 않거나 작동이 중단 될 수 있습니다. 공격자가 응용 프로그램과 함께 DLL을 공장 화 하는 경우 로컬 코드 실행을 달성할 수 있습니다.

### <a name="other-dataadapter-types"></a>기타 DataAdapter 형식

타사 구현에서는 `DataAdapter` 신뢰할 수 없는 입력을 통해 제공 되는 보안 보증에 대 한 자체 평가를 수행 해야 합니다. .NET에서는 이러한 구현과 관련 된 안전을 보장할 수 없습니다.

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a>ReadXml 및 DataTable. ReadXml

`DataSet.ReadXml`및 `DataTable.ReadXml` 메서드는 신뢰할 수 없는 입력과 함께 사용할 경우 안전 하지 않습니다. 대신이 문서의 뒷부분에서 설명 하는 대체 방법 중 하나를 사용 하는 것이 좋습니다.

및의 구현은 `DataSet.ReadXml` `DataTable.ReadXml` serialization 취약점이 잘 이해 된 위협 범주 였습니다. 따라서 코드는 현재 보안 모범 사례를 따르지 않습니다. 이러한 Api는 공격자가 웹 앱에 대해 DoS 공격을 수행할 수 있는 벡터로 사용 될 수 있습니다. 이러한 공격으로 인해 웹 서비스가 응답 하지 않거나 예기치 않은 프로세스가 종료 될 수 있습니다. 프레임 워크는 이러한 공격 범주에 대 한 완화를 제공 하지 않으며 .NET은이 동작을 "의도적으로" 고려 합니다.

.NET은 및에서 정보 공개 또는 원격 코드 실행과 같은 일부 문제를 완화 하기 위해 보안 업데이트를 릴리스 했습니다 `DataSet.ReadXml` `DataTable.ReadXml` . .NET 보안 업데이트는 이러한 위협 범주에 대 한 완전 한 보호를 제공 하지 않을 수 있습니다. 소비자는 개별 시나리오를 평가하고 이러한 위험에 노출될 가능성을 고려해야 합니다.

소비자는 이러한 Api에 대 한 보안 업데이트가 일부 상황에서 응용 프로그램 호환성에 영향을 줄 수 있음을 알고 있어야 합니다. 또한 이러한 Api의 novel 취약성은 .NET에서 실제로 보안 업데이트를 게시할 수 없는 것으로 검색 될 가능성이 있습니다.

이러한 Api의 소비자는 다음 중 하나를 수행 하는 것이 좋습니다.

* 이 문서의 뒷부분에 설명 된 대체 방법 중 하나를 사용 하는 것이 좋습니다.
* 앱에서 개별 위험 평가를 수행 합니다.

이러한 Api를 활용할 지 여부를 결정 하는 것은 소비자의 책임입니다. 소비자는 이러한 Api를 사용 하 여 제공할 수 있는 규정 요구 사항을 비롯 하 여 보안, 기술 및 법적 위험을 평가 해야 합니다.

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a>ASP.NET 웹 서비스 또는 WCF를 통한 DataSet 및 DataTable

`DataSet` `DataTable` 다음 코드에서 보여 주는 것 처럼 ASP.NET (SOAP) 웹 서비스에서 또는 인스턴스를 받아들일 수 있습니다.

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

이에 대 한 변형은 `DataSet` `DataTable` 다음 코드에 표시 된 것 처럼 전체 SOAP 직렬화 된 개체 그래프의 일부로이를 허용 하는 대신 또는 매개 변수로 사용할 수 없습니다.

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

또는 ASP.NET 웹 서비스 대신 WCF를 사용 합니다.

```cs
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

이러한 모든 경우에 위협 모델 및 보안 보장은 [ReadXml 및 ReadXml 섹션과](#dsrdtr)동일 합니다.

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a>XmlSerializer를 통해 데이터 집합 또는 DataTable Deserialize

개발자는 `XmlSerializer` 다음 코드와 같이를 사용 하 여 `DataSet` 및 인스턴스를 deserialize 할 수 있습니다 `DataTable` .

```cs
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

이러한 경우 위협 모델 및 보안 보장은 [ReadXml 및 ReadXml 섹션과](#dsrdtr) 동일 합니다.

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a>JsonConvert를 통해 데이터 집합 또는 DataTable Deserialize

다음 코드에 표시 된 것 처럼 인기 있는 타사 Newtonsoft.json library [JSON.NET](https://www.newtonsoft.com/json) 를 사용 하 여 `DataSet` 및 인스턴스를 deserialize 할 수 있습니다 `DataTable` .

```cs
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

`DataSet` `DataTable` 트러스트 되지 않은 JSON blob에서 또는를이 방식으로 deserialize 하는 것은 안전 하지 않습니다. 이 패턴은 서비스 거부 공격에 취약 합니다. 이러한 공격으로 인해 앱이 중단 되거나 응답 하지 않을 수 있습니다.

> [!NOTE]
> Microsoft는 _Newtonsoft.Js_와 같은 타사 라이브러리의 구현을 보증 하거나 지원 하지 않습니다. 이 정보는 완전성을 위해 제공 되며이 정보를 작성 하는 시간을 정확 하 게 제공 합니다.

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a>BinaryFormatter를 통해 데이터 집합 또는 DataTable Deserialize

개발자 `BinaryFormatter` `NetDataContractSerializer` 는,, `SoapFormatter` 또는 관련 된 ***unsafe*** 포맷터를 사용 하 여 `DataSet` `DataTable` 신뢰할 수 없는 페이로드에서 또는 인스턴스를 deserialize 해서는 안 됩니다.

* 이는 전체 원격 코드 실행 공격에 취약 합니다.
* `SerializationBinder`이러한 공격을 방지 하기 위해 사용자 지정을 사용 하는 것 만으로는 충분 하지 않습니다.

## <a name="safe-replacements"></a>안전한 대체

다음 중 하나에 해당 하는 앱:

* `DataSet` `DataTable` .Asmx SOAP 끝점 또는 WCF 끝점을 허용 합니다.
* 신뢰할 수 없는 데이터를 또는 인스턴스로 `DataSet` Deserialize `DataTable` 합니다.

[Entity Framework](/ef)사용 하려면 개체 모델을 대체 하는 것이 좋습니다. Entity Framework:

* 는 관계형 데이터를 나타낼 수 있는 풍부 하 고 현대적인 개체 지향 프레임 워크입니다.
* 는 데이터베이스 공급자의 [다양 한 에코 시스템](/ef/core/providers/) 을 제공 하 여 Entity Framework 개체 모델을 통해 쉽게 데이터베이스 쿼리를 수행할 수 있도록 합니다.
* 는 신뢰할 수 없는 소스의 데이터를 deserialize 할 때 기본 제공 보호 기능을 제공 합니다.

SOAP 끝점을 사용 하는 앱의 경우 `.aspx` [WCF](/dotnet/framework/wcf/)를 사용 하도록 해당 끝점을 변경 하는 것이 좋습니다. WCF는 웹 서비스에 대 한 보다 완전 한 기능을 갖춘 대체 기능입니다 `.asmx` . WCF 끝점은 기존 호출자와의 호환성을 위해 [SOAP를 통해 노출 될 수 있습니다](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) .

## <a name="code-analyzers"></a>코드 분석기

소스 코드를 컴파일할 때 실행 되는 코드 분석기 보안 규칙은 c # 및 Visual Basic 코드에서이 보안 문제와 관련 된 취약성을 찾는 데 도움이 될 수 있습니다. FxCopAnalyzers는 [nuget.org](https://www.nuget.org/)에 배포 되는 코드 분석기의 NuGet 패키지입니다.

코드 분석기의 개요는 [소스 코드 분석기 개요](https://docs.microsoft.com/visualstudio/code-quality/roslyn-analyzers-overview)를 참조 하세요.

다음 FxCopAnalyzers 규칙을 사용 하도록 설정 합니다.

- [CA2350](https://docs.microsoft.com/visualstudio/code-quality/ca2350): 신뢰할 수 없는 데이터와 함께 ReadXml ()를 사용 하지 마십시오.
- [CA2351](https://docs.microsoft.com/visualstudio/code-quality/ca2351): 신뢰할 수 없는 데이터와 ReadXml ()를 사용 하지 마십시오.
- [CA2352](https://docs.microsoft.com/visualstudio/code-quality/ca2352): 안전 하지 않은 데이터 집합 또는 serialize 할 수 있는 형식의 DataTable은 원격 코드 실행 공격에 취약할 수 있습니다.
- [CA2353](https://docs.microsoft.com/visualstudio/code-quality/ca2353): serializable 형식의 안전 하지 않은 데이터 집합 또는 DataTable
- [CA2354](https://docs.microsoft.com/visualstudio/code-quality/ca2354): deserialize 된 개체 그래프의 안전 하지 않은 데이터 집합 또는 DataTable은 원격 코드 실행 공격에 취약할 수 있습니다.
- [CA2355](https://docs.microsoft.com/visualstudio/code-quality/ca2355): deserialize 가능한 개체 그래프에 안전 하지 않은 데이터 집합 또는 DataTable 형식이 있습니다.
- [CA2356](https://docs.microsoft.com/visualstudio/code-quality/ca2356): web deserialize 가능한 개체 그래프의 안전 하지 않은 데이터 집합 또는 DataTable 형식
- [CA2361](https://docs.microsoft.com/visualstudio/code-quality/ca2361): ReadXml ()를 포함 하는 자동 생성 된 클래스가 신뢰할 수 없는 데이터와 함께 사용 되지 않는지 확인 합니다.
- [CA2362](https://docs.microsoft.com/visualstudio/code-quality/ca2362): 자동 생성 serialize 할 수 있는 형식에서 안전 하지 않은 데이터 집합 또는 DataTable은 원격 코드 실행 공격에 취약할 수 있습니다.

규칙을 구성 하는 방법에 대 한 자세한 내용은 [코드 분석기 사용](https://docs.microsoft.com/visualstudio/code-quality/use-roslyn-analyzers)을 참조 하세요.

새 보안 규칙은 다음 NuGet 패키지에서 사용할 수 있습니다.

- FxCopAnalyzers 3.3.0: Visual Studio 2019 버전 16.3 이상
- FxCopAnalyzers 2.9.11: Visual Studio 2017 버전 15.9 이상
