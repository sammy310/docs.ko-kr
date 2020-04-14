---
title: 앱컨텍스트스위치오버라이드 요소
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 95ae438e9fb52cc584d18a981bffb66147eb4a77
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242818"
---
# <a name="appcontextswitchoverrides-element"></a>\<앱컨텍스트스위치> 요소

<xref:System.AppContext> 클래스에 사용되는 스위치를 하나 이상 정의하여 새 기능의 옵트아웃 메커니즘을 제공합니다.

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<앱컨텍스트스위치오버라이드>**

## <a name="syntax"></a>구문

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|attribute|Description|
|---------------|-----------------|
|`value`|필수 특성입니다.<br /><br /> 하나 이상의 스위치 이름과 관련 부울 값을 정의합니다.|

### <a name="value-attribute"></a>값 속성

|값|설명|
|-----------|-----------------|
|"이름=값"|값 (또는)과`true` `false`함께 미리 정의된 스위치 이름입니다. 여러 스위치 이름/값 쌍은 세미콜론(";")으로 구분됩니다. .NET Framework에서 지원하는 미리 정의된 스위치 이름 목록은 설명 섹션을 참조하십시오.|

### <a name="child-elements"></a>자식 요소
 없음

### <a name="parent-elements"></a>부모 요소

|요소|Description|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>설명
 .NET Framework 4.6부터 구성 `<AppContextSwitchOverrides>` 파일의 요소를 통해 API 호출자는 앱이 새 기능을 활용할 수 있는지 또는 이전 버전의 라이브러리와의 호환성을 유지할 수 있는지 여부를 결정할 수 있습니다. 예를 들어 API의 동작이 두 버전의 라이브러리 간에 변경된 경우 `<AppContextSwitchOverrides>` 요소는 해당 API의 호출자가 새 기능을 지원하는 라이브러리 버전의 새 동작을 옵트아웃할 수 있도록 합니다. .NET Framework에서 API를 호출하는 앱의 경우 `<AppContextSwitchOverrides>` 이 요소는 앱이 해당 기능을 포함하는 .NET Framework 버전에서 실행되는 경우 이전 버전의 .NET Framework를 대상으로 하는 호출자가 새 기능을 옵트인하도록 허용할 수도 있습니다.

 `<AppContextSwitchOverrides>` 요소의 특성은 `value` 하나 이상의 세미콜론으로 구분된 이름/값 쌍으로 구성된 단일 문자열로 구성됩니다.  각 이름은 호환성 스위치를 식별하고 해당 값은 스위치가 `false`설정되어 있는지 여부를 나타내는 부울(또는)입니다.`true` 기본적으로 스위치는 `false`은 이며 라이브러리는 새 기능을 제공 합니다. 스위치가 설정된 경우에만 이전 기능을 제공합니다(즉, 해당 `true`값은). 이렇게 하면 라이브러리가 기존 API에 대한 새 동작을 제공하는 동시에 이전 동작에 의존하는 호출자가 새 기능을 옵트아웃할 수 있습니다.

 .NET 프레임워크는 다음 스위치를 지원합니다.

|이름 전환|Description|도입|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Windows 프레젠테이션 재단이 레거시를 컨트롤 레이아웃에 알고리즘으로 사용하는지 여부를 제어합니다. 자세한 내용은 [완화: WPF 레이아웃](../../../migration-guide/mitigation-wpf-layout.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|PackageDigitalSignatureManager에서 패키지 의 일부를 서명하는 데 사용되는 기본 알고리즘이 SHA1인지 SHA256인지 여부를 제어합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|`false`로 설정하면 FIPS가 활성화된 경우 Visual Studio를 사용하여 XAML 기반 워크플로 프로젝트를 디버깅할 수 있습니다. 그렇지 않으면 <xref:System.NullReferenceException> System.Activities 어셈블리의 메서드에 대한 호출에서 a가 throw됩니다.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|디버거에서 워크플로 인스턴스에 대한 체크섬이 MD5 또는 SHA1을 사용하는지 여부를 제어합니다. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|워크플로 체크섬 해시가 .NET Framework 4.7()에서 기본값으로`true`도입된 SHA1 알고리즘을 사용하는지 또는 .NET Framework 4.8()에서`false`기본값으로 도입된 기본 SHA256 알고리즘을 사용하는지 여부를 제어합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|휴대용 PDF를 사용할 때 스택 추적이 원본 파일 및 라인 정보를 포함할 수 있는지 여부를 제어합니다. `false`소스 파일 및 줄 정보를 포함합니다. 그렇지 `true`않으면 .|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|개체에 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> PNG 프레임이 있을 <xref:System.Drawing.Icon> 때 메서드가 예외를 throw하는지 여부를 제어합니다. 자세한 내용은 [완화: 아이콘 개체의 PNG 프레임](../../../migration-guide/mitigation-png-frames-in-icon-objects.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|메서드에 <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> 의해 컬렉션에 추가될 때 개체가 올바르게 삭제되는지 여부를 결정합니다. <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> `true`레거시 동작을 유지하기 위해; `false` 을 사용하여 모든 개인 글꼴 개체를 삭제합니다. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|의 성능이 네트워크 <xref:System.Windows.Forms.PrintPreviewDialog> 프린터에 최적화되어 있는지 여부를 제어합니다. 자세한 내용은 [PrintPreviewDialog 컨트롤 개요를](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)참조하십시오.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|일본어 달력 연도에 대한 연도 범위 검사가 적용되는지 여부를 제어합니다. `true`을 적용하여 연도 `false` 범위 검사를 적용하고 이를 비활성화합니다(기본 동작). 자세한 내용은 [캘린더 작업을 참조하십시오.](../../../../standard/datetime/working-with-calendars.md)|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|구문 분석 작업에서 일본어 달력 시대의 첫 해로 "1"만 인식되는지 여부를 제어합니다. `true`"1"만 인식하기 위해; `false` 을 사용하여 "1" 또는 Gannen(기본 동작)을 인식합니다. 자세한 내용은 [캘린더 작업을 참조하십시오.](../../../../standard/datetime/working-with-calendars.md)|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|일본어 달력 시대의 첫 해가 서식 작업에서 "1"또는 Gannen으로 표시되는지 여부를 제어합니다. `true`시대의 첫 해를 "1"로 포맷합니다. `false` 을 사용하여 Gannen(기본 동작)으로 포맷할 수 있습니다. 자세한 내용은 [캘린더 작업을 참조하십시오.](../../../../standard/datetime/working-with-calendars.md)|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|비동기 작업이 호출 스레드의 컨텍스트에서 흐르지 않는지 여부를 제어합니다. 자세한 내용은 [현재 문화 및 현재 UICulture 작업을](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)참조하십시오.|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|메서드가 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 클레임 형식과 마지막 DNS 항목만 일치시키려고 시도하는지 여부를 제어합니다. 자세한 내용은 [완화: X509CertificateClaimSet.FindClaims 메서드](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)를 참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|권한 부여Context.Empty가 변경 가능한 개체를 반환하도록 허용할지 여부를 제어합니다.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|(260자)보다 `MAX_PATH` 긴 패스가 <xref:System.IO.PathTooLongException>를 throw할지 여부를 제어합니다. 자세한 내용은 [긴 경로 지원](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)을 참조하십시오.|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|<xref:System.IO.Compression.DeflateStream> 네이티브 OS 루틴이 클래스에서 압축 해제에 사용되는지 여부를 제어합니다. `false`네이티브 API를 사용하려면 `true` 을 사용하여 <xref:System.IO.Compression.DeflateStream> 구현을 사용합니다.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|백슬래시("")를\\속성의 경로 구분기호로 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> 사용하여 정방향 슬래시("/")를 사용합니다. 자세한 내용은 [완화: ZipArchiveEntry.전체 이름 경로 구분 기호를](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|<xref:System.IO.Ports.SerialPort> 스트림으로 만든 백그라운드 스레드에 throw되는 운영 체제 예외가 프로세스를 종료하는지 여부를 제어합니다.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|레거시 경로 정규화가 사용되는지 여부와 및 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 메서드에서 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> URI 경로가 지원되는지 여부를 제어합니다. 자세한 내용은 [완화: 경로 정규화](../../../migration-guide/mitigation-path-normalization.md) 및 [완화: 경로 콜론 검사](../../../migration-guide/mitigation-path-colon-checks.md)를 참조하십시오.|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|같음 테스트가 한 개체의 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> 속성을 두 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> 번째 개체의 속성과 비교하는지 여부를 제어합니다. 자세한 내용은 [MemberDescriptor.Equals의 잘못된 구현을](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)참조하십시오.|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|인증서 강화 키 사용 (EKU) 개체 식별자 (OID) 유효성 검사를 사용 하지 않도록 설정 합니다. EKU(향상된 키 사용) 확장은 키를 사용하는 애플리케이션을 나타내는 OID(개체 식별자)의 모음입니다.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|SCH_SEND_AUX_RECORD 사용을 비활성화하여 SSL/TLS(BEAST) 완화에 대한 TLS1.0 브라우저 악용을 비활성화합니다.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|클래스가 <xref:System.Net.ServicePointManager?displayProperty=nameWithType> <xref:System.Net.Security.SslStream?displayProperty=nameWithType> SSL 3.0 프로토콜을 사용할 수 있는지 여부를 제어합니다. 자세한 내용은 [완화: TLS 프로토콜](../../../migration-guide/mitigation-tls-protocols.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|시스템기본 TLS 버전을 Tls12, Tls11, Tls의 기본값으로 되돌리지 않도록 설정합니다.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|SslStream TLS 서버 측 경고를 사용하지 않도록 설정합니다.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|COM interop 이벤트의 ByRef SafeArray 매개 변수가 기본`false`코드()로 마샬링되는지 또는`true`네이티브 코드로 다시 마샬링할 수 있는지()를 제어합니다.|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |[DataContractJson Serializer가](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) ECMAScript V6 및 V8 표준을 기반으로 일부 제어 문자를 직렬화하는지 여부를 제어합니다. 자세한 내용은 [완화: DataContractJsonSerializer로 제어 문자 serialization](../../../migration-guide/mitigation-serialization-control-characters.md)을 참조하세요.| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|표준 시간대에 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 대해 여러 조정을 지원하는지 또는 단일 조정만 지원하는지 여부를 제어합니다. 을 `true`사용하여 <xref:System.TimeZoneInfo> 날짜 및 시간 데이터를 직렬화하고 디serialize하는 경우 그렇지 않으면 여러 <xref:System.TimeZone> 조정 규칙을 지원하지 않는 형식을 사용합니다.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|개체 <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType> 직렬화 및 역직렬화 중에 더 큰 배열 크기를 사용하는지 여부를 제어합니다. 이 스위치를 `true` 설정하여 큰 개체 그래프의 직렬화 및 직렬화 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>성능을 예: 유형별로 설정합니다. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29> 생성자가 기존 개체 참조를 사용 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> 하 고 새 개체의 속성을 설정 하는지 여부를 제어 합니다. 자세한 내용은 [완화: ClaimsIdentity 생성자](../../../migration-guide/retargeting/4.6.1-4.6.2.md)를 참조하세요.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|<xref:System.Security.Cryptography.AesCryptoServiceProvider> 암호 해독기를 다시 사용하려는 시도가 <xref:System.Security.Cryptography.CryptographicException>을 throw하는지 여부를 제어합니다. 자세한 내용은 [AesCryptoServiceProvider 암호 해독기가 재사용 가능한 변환을 제공합니다.](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|[CspParameters.ParentWindowHandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) 속성의 값이 창 핸들의 메모리 위치를 나타내는 [IntPtr인지](xref:System.IntPtr) 또는 창 핸들(HWND)인지 여부를 제어합니다. 자세한 내용은 [완화: CspParameters.ParentWindowHandle에 HWND 필요](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value)를 참조하세요. |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|FIPS 모드에서 관리되는 암호화 클래스를 사용하는 것이 <xref:System.Security.Cryptography.CryptographicException> `true`() ()를 throw하는지 또는`false`시스템 라이브러리()의 구현에 의존하는지 여부를 제어합니다.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|일부 SignedCMS 작업의 기본값이 SHA1인지 SHA256인지 결정합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|메서드가 <xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> 운영 체제()`false`에서 지원하는 모든 명명된 곡선을 올바르게 처리하는지 또는 레거시 동작으로 되돌릴지 여부를 제어합니다.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|일부 SignedXML 작업의 기본값이 SHA1인지 SHA256인지 확인합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|보안 모드가 `TransportWithMessageCredential` 서명되지 않은 "to" 헤더가 있는 메시지를 허용하는지 여부를 결정합니다. 옵트인 스위치입니다. 자세한 내용은 [.NET 프레임워크 4.6.1의 런타임 변경](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf)사항을 참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|<xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> 생성자가 요소 중 하나가 <xref:System.ArgumentException> `null`있는 경우 throw하는지 여부를 제어합니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|CSG 키 저장소 공급자와 함께 X509 인증서를 사용하려고 시도하는 것이 예외를 throw하는지 여부를 결정합니다. 자세한 내용은 [CNG를 사용하여 저장된 WCF 전송 보안 지원 인증서를](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|자체 호스팅 서비스와 함께 HTTP 전송을 사용하는 경우 `true` 이 값을 설정하면 WCF가 요청에 대한 응답 헤더에 헤더를 `Connection: close` 추가하는 응용 프로그램을 무시합니다. 이 값을 `false` 설정하면 `Connection: close` 응답 헤더에 헤더를 추가할 수 있으므로 응답을 보낸 후 요청 소켓이 닫힙어집니다.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|다시 진입 하는 서비스의 인스턴스를 한 번에 단일 실행 스레드로 제한 하여 발생 하는 교착 상태를 처리 합니다.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|이와 `Switch.System.Net.DontEnableSchUseStrongCrypto`함께 WCF 메시지 보안에서 TLS 1.1 및 TLS 1.2를 사용하는지 여부를 결정합니다.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|값은 `false` 운영 체제가 프로토콜을 선택할 수 있도록 기본 구성을 설정합니다. 값은 `true` 기본값을 사용 가능한 가장 높은 프로토콜로 설정합니다. (이전 프레임워크 버전의 서비스 분기에도 사용 가능)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|WCF의 MSMQ 메시지에 대한 기본 메시지 서명 알고리즘이 SHA1인지 SHA256인지 여부를 결정합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|WCF가 SHA1 또는 SHA256 해시를 사용하여 명명된 파이프에 대한 임의의 이름을 생성하는지 여부를 제어합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|예외 메시지가 null인 경우 [NullReferenceException을](xref:System.NullReferenceException) throw할지 여부를 제어합니다.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|서비스 시작시 throw된 예외가 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> 메서드의 호출자에게 전파되는지 여부를 제어합니다.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|인스턴스가 <xref:System.Threading.Timer> 대규모 환경에서 성능 향상을 활용하는지 여부를 제어합니다. 성능 `true`향상이 활성화된 경우. (기본값) `false` 비활성화됩니다.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|디코딩된 특정 백분율 인코딩 된 문자가 이제 일관되게 인코딩된 상태로 남아 있는지 여부를 결정합니다. 이 `true`경우 디코딩됩니다. 그렇지 `false`않으면 .|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|URI에서 유니코드 양방향 문자의 처리를 결정합니다. `true`URI에서 그들을 제거; `false` 보존하고 백분율 인코딩할 수 있습니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |Windows 프레젠테이션 재단이`true``false` \*-column에 공간을 할당할 때 이전 알고리즘() 또는 새 알고리즘()을 적용하는지 여부를 결정합니다. 자세한 내용은 [완화: Grid 컨트롤의 별 열 공간 할당](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns)을 참조하세요. |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|선택기 또는 탭 컨트롤이 선택 변경된 이벤트를 발생하기 전에 선택기 또는 탭 컨트롤이 항상 선택한 값 속성의 값을 업데이트하는지 여부를 제어합니다.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|표시가 <xref:System.Windows.Controls.TextBox> 아닌 선택 렌더링을 사용할 수 있는지 <xref:System.Windows.Controls.PasswordBox> 여부와 컨트롤에서 가려진`false`텍스트()를 방지할지 또는 표시기`true`레이어()에서만 텍스트가 렌더링되는지 여부를 결정합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|사용자 지정 IList 인덱서가`true`클래스에서 잘못() 또는 올바르게 ()`false`사용되는지 여부를 제어합니다. <xref:System.Windows.Data.Binding?displayProperty=nameWithType>|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|DPI 변경이 `false`시스템별(값) 또는 모니터별 `true`기준(값)에서 발생하는지 여부를 결정합니다.|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|WPF가 모니터별 인식 모드에서 <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType> 실행될 때 컨트롤의 크기 조정이 비활성화되어 있는지()`true`또는 활성화()인지`false`여부를 제어합니다.|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|컨트롤 텍스트가 있을 때 개발자가 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 특별히 처리해야 하는지 여부를 결정합니다. `true`<xref:System.Windows.Forms.DomainUpDown.UpButton> 작업을 처리하기 위해; `false` <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업이 제대로 동기화될 수 있도록 합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 메서드가 호출될 때 예외를 throw하지 않고 메시지를 안전하게 필터링할 수 있는 코드를 옵트아웃합니다. 자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|사용자가 중첩된 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤에서 메뉴를 열 때 속성이 소스 컨트롤을 반환하는지 여부를 확인합니다. `true`반환할 `null`레거시 동작입니다. `false` 을 사용하여 소스 컨트롤을 반환합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|도구 설명 호출 지원이 비활성화되어`true`있는지()`false`또는 사용 가능()인지 제어합니다. 도구 설명 호출 지원을 사용하도록 설정하려면 에 `Switch.UseLegacyAccessibilityFeatures` `Switch.UseLegacyAccessibilityFeatures.2`의해 `Switch.UseLegacyAccessibilityFeatures.3` 정의된 레거시 접근성 `false`기능도 필요하며 모두 비활성화(로 설정됨)가 필요합니다.|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|WPF 응용 `WM_POINTER`프로그램에서 선택적 기반 터치/스타일러스 스택이 활성화되어 있는지 여부를 결정합니다. 자세한 내용은 [완화: 포인터 기반 터치 및 스타일러스 지원](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md) 참조|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|검사에 사용되는 기본 해시 알고리즘이 SHA256(SHA1)`false`또는 SHA1()인지`true`확인합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|예외의 원인을 보다 구체적으로 나타내는 예외 대신 레거시 [NullReferenceException이](xref:System.NullReferenceException) throw되는지 여부를 제어합니다(예: [DirectoryNotFoundException](xref:System.IO.DirectoryNotFoundException) 또는 [FileNotFoundException](xref:System.IO.FileNotFoundException). [NullReference 예외](xref:System.NullReferenceException)를 처리 에 따라 달라 집니다 코드에서 사용 하기 위한 것입니다. | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|워크플로 프로젝트 빌드에서 XOML 파일의 체크섬 해시가 MD5`true`알고리즘()을 사용하는지 또는 .NET Framework 4.8에서 기본값으로 도입된 SHA256 알고리즘을 사용하는지 여부를 제어합니다.<br>MD5 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|SqlTrackingService의 체크섬 해시가 캐시된 문자열에 MD5 알고리즘()을`true`사용하는지 또는 .NET Framework 4.8에서 기본값으로 도입된 SHA256 알고리즘을 사용하는지 여부를 제어합니다.<br>MD5 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|워크플로 런타임에 의한 체크섬 해시가 캐시된`true`워크플로 정의에 MD5 알고리즘()을 사용하는지 또는 .NET Framework 4.8에서 기본값으로 도입된 SHA256 알고리즘을 사용하는지 여부를 제어합니다.<br>MD5 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|.NET Framework 4.7.1부터 사용할 수 있는 내게 필요한 옵션 기능을 사용할 수 있는지 여부를 제어합니다. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|.NET Framework 4.7.2에서 사용할 수 있는`false`내게 필요한`true`옵션 기능이 사용 가능할지() 또는 사용 안 함()인지 제어합니다. .NET `Switch.UseLegacyAccessibilityFeatures` Framework `true` 4.7.1 내게 필요한 옵션 기능을 사용하도록 설정해야 하는 경우 `true`|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|.NET Framework 4.8에 도입된 내게`false`필요한 옵션`true`기능이 사용 가능여부() 또는 사용 안 함()을 제어합니다. `true` `Switch.UseLegacyAccessibilityFeatures` 을 `Switch.UseLegacyAccessibilityFeatures.2` 준수해야 합니다. `true`|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|사용자가 WPF 컨트롤(WPF`true`컨트롤)을 통해 마우스 커서를 마우스 커서를 마우스로 가리키는 경우 도구 설명이`false`표시되는지 또는 키보드 포커스와 키보드 단축키 키(기본 동작)를 통해 둘 다 표시되는지 여부를 제어합니다. .NET Framework 4.8에서 실행되지만 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램의 경우 `Switch.UseLegacyAccessibilityFeatures`키보드 `Switch.UseLegacyAccessibilityFeatures.2`포커스와 바로 가기 키 지원을 모두 사용하도록 설정하려면 을 설정하고 `Switch.UseLegacyAccessibilityFeatures.3` 모두 로 `false`설정합니다.|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|복합 키의 빈 키 시퀀스가 XSD 스키마 유효성 검사에서 무시되는지 여부를 제어합니다. 자세한 내용은 [완화: XML 스키마 유효성 검사를](../../../migration-guide/mitigation-xml-schema-validation.md)참조하십시오.|.NET Framework 4.6|

> [!NOTE]
> 응용 프로그램 `AppContextSwitchOverrides` 구성 파일에 요소를 추가하는 대신 (C#) 또는 `static` `Shared` (Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 스위치를 설정할 수도 있습니다.

 라이브러리 개발자는 사용자 지정 스위치를 정의하여 호출자가 라이브러리의 이후 버전에 도입된 변경된 기능을 옵트아웃할 수 있도록 할 수도 있습니다. 자세한 내용은 <xref:System.AppContext> 클래스를 참조하세요.

## <a name="switches-in-aspnet-applications"></a>ASP.NET 애플리케이션의 스위치

web.config 파일의 [ \<appSettings>](../appsettings/index.md) 섹션에 [ \<추가>](../appsettings/add-element-for-appsettings.md) 요소를 추가하여 호환성 설정을 사용하도록 ASP.NET 응용 프로그램을 구성할 수 있습니다.

다음 예제에서는 `<add>` 요소를 사용하여 web.config 파일의 섹션에 `<appSettings>` 두 가지 설정을 추가합니다.

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>예제

 다음 예제에서는 `AppContextSwitchOverrides` 요소를 사용하여 비동기 메서드 `Switch.System.Globalization.NoAsyncCurrentCulture`호출에서 문화가 스레드 간에 흐르는 것을 방지하는 단일 응용 프로그램 호환성 스위치를 정의합니다.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 다음 예제에서는 `AppContextSwitchOverrides` 요소를 사용하여 두 개의 응용 `Switch.System.Globalization.NoAsyncCurrentCulture` `Switch.System.IO.BlockLongPaths`프로그램 호환성 스위치 및 을 정의합니다. 세미콜론은 두 이름/값 쌍을 구분합니다.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>참고 항목

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<런타임> 요소](runtime-element.md)
- [\<구성> 요소](../configuration-element.md)
