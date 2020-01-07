---
title: AppContextSwitchOverrides 요소
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- AppContextSwitchOverrides
- compatibility switches
- configuration switches
- configuration
ms.assetid: 4ce07f47-7ddb-4d91-b067-501bd8b88752
ms.openlocfilehash: 2495ddbc89caf0b72cfc0e6a1647e8f2da291778
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347190"
---
# <a name="appcontextswitchoverrides-element"></a>\<AppContextSwitchOverrides > 요소

<xref:System.AppContext> 클래스에 사용되는 스위치를 하나 이상 정의하여 새 기능의 옵트아웃 메커니즘을 제공합니다.

[ **\<configuration>** ](../configuration-element.md)\
[ **\<런타임 >** ](runtime-element.md) &nbsp;&nbsp;\
&nbsp;&nbsp;&nbsp;&nbsp; **\<AppContextSwitchOverrides>**

## <a name="syntax"></a>구문

```xml
<AppContextSwitchOverrides value="name1=value1[[;name2=value2];...]" />
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|`value`|필수 특성입니다.<br /><br /> 하나 이상의 스위치 이름 및 연결 된 부울 값을 정의 합니다.|

### <a name="value-attribute"></a>value 특성

|값|설명|
|-----------|-----------------|
|"name=value"|값 (`true` 또는 `false`)과 함께 미리 정의 된 스위치 이름입니다. 여러 스위치 이름/값 쌍은 세미콜론 (";")으로 구분 됩니다. .NET Framework에서 지 원하는 미리 정의 된 스위치 이름 목록은 설명 섹션을 참조 하세요.|

### <a name="child-elements"></a>자식 요소
 없음.

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|

## <a name="remarks"></a>주의
 .NET Framework 4.6부터 구성 파일의 `<AppContextSwitchOverrides>` 요소를 사용 하면 API 호출자가 앱이 새로운 기능을 활용 하거나 이전 라이브러리 버전과의 호환성을 유지할 수 있는지 여부를 확인할 수 있습니다. 예를 들어 두 라이브러리 버전 간에 API 동작이 변경 된 경우 `<AppContextSwitchOverrides>` 요소를 사용 하면 해당 API의 호출자가 새 기능을 지 원하는 라이브러리 버전에서 새로운 동작을 옵트아웃 (opt out) 할 수 있습니다. .NET Framework Api를 호출 하는 앱의 경우, `<AppContextSwitchOverrides>` 요소는 해당 앱이 해당 기능을 포함 하는 .NET Framework 버전에서 실행 되는 경우 새 기능을 사용 하 여 앱이 이전 버전의 .NET Framework를 대상으로 하는 호출자를 허용할 수도 있습니다.

 `<AppContextSwitchOverrides>` 요소의 `value` 특성은 하나 이상의 세미콜론으로 구분 된 이름/값 쌍으로 구성 된 단일 문자열로 구성 됩니다.  각 이름은 호환성 스위치를 식별 하 고 해당 값은 스위치가 설정 되었는지 여부를 나타내는 부울 (`true` 또는 `false`)입니다. 기본적으로 스위치는 `false`되며 라이브러리는 새로운 기능을 제공 합니다. 스위치가 설정 된 경우 (즉, 해당 값이 `true`) 이전 기능만 제공 합니다. 이렇게 하면 이전 동작에 의존 하는 호출자가 새 기능을 옵트아웃 (opt out) 할 수 있도록 하는 동시에 라이브러리에서 기존 API에 대 한 새로운 동작을 제공할 수 있습니다.

 .NET Framework는 다음 스위치를 지원 합니다.

|스위치 이름|설명|도입|
|-----------------|-----------------|----------------|
|`Switch.MS.Internal.`<br/>`DoNotApplyLayoutRoundingToMarginsAndBorderThickness`|Windows Presentation Foundation에서 컨트롤 레이아웃에 대해 레거시 알고리즘을 사용할지 여부를 제어 합니다. 자세한 내용은 [완화: WPF 레이아웃](../../../migration-guide/mitigation-wpf-layout.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.MS.Internal.`<br/>`UseSha1AsDefaultHashAlgorithmForDigitalSignatures`|PackageDigitalSignatureManager에서 패키지의 일부에 서명 하는 데 사용 되는 기본 알고리즘이 SHA1 또는 s h a 1 인지 여부를 제어 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.Activities.`<br/>`UseMD5CryptoServiceProviderForWFDebugger`|`false`로 설정 된 경우 FIPS를 사용 하도록 설정 된 경우 Visual Studio를 사용 하 여 XAML 기반 워크플로 프로젝트를 디버그할 수 있습니다. 이를 제외 하 고, <xref:System.NullReferenceException>는 System.object 어셈블리의 메서드 호출에서 throw 됩니다.|.NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseMD5ForWFDebugger`|디버거의 워크플로 인스턴스에 대 한 체크섬이 MD5 또는 SHA1을 사용 하는지 여부를 제어 합니다. | .NET Framework 4.7|
|`Switch.System.Activities.`<br/>`UseSHA1HashForDebuggerSymbols`|워크플로 체크섬 해시가 .NET Framework 4.7 (`true`)에서 기본값으로 도입 된 SHA1 알고리즘을 사용 하는지 또는`false`(.NET Framework 4.8)에서 기본값으로 도입 된 기본 SHA256 알고리즘을 사용 하는지 여부를 제어 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.System.Diagnostics.`<br/>`IgnorePortablePDBsInStackTraces`|이식 가능 Pdb를 사용할 때 스택 추적에서 가져올 것인지 여부를 제어 합니다. 소스 파일 및 줄 정보를 포함할 수 있습니다. 소스 파일 및 줄 정보를 포함 하려면 `false` 합니다. 그렇지 않으면 `true`합니다.|.NET Framework 4.7.2|
|`Switch.System.Drawing.`<br/>`DontSupportPngFramesInIcons`|<xref:System.Drawing.Icon> 개체에 PNG 프레임이 있을 때 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드에서 예외를 throw 하는지 여부를 제어 합니다. 자세한 내용은 [완화: 아이콘 개체의 PNG 프레임](../../../migration-guide/mitigation-png-frames-in-icon-objects.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.System.Drawing.Text.`<br/>`DoNotRemoveGdiFontsResourcesFromFontCollection`|<xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType> 메서드에 의해 컬렉션에 추가 될 때 <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> 개체가 제대로 삭제 되는지 여부를 확인 합니다. 레거시 동작을 유지 하는 `true` 모든 전용 글꼴 개체를 삭제 하려면 `false` 합니다. |.NET Framework 4.7.2|
|`Switch.System.Drawing.Printing.`<br>`OptimizePrintPreview`|<xref:System.Windows.Forms.PrintPreviewDialog>의 성능이 네트워크 프린터에 최적화 되어 있는지 여부를 제어 합니다. 자세한 내용은 [PrintPreviewDialog 컨트롤 개요](../../../winforms/controls/printpreviewdialog-control-overview-windows-forms.md)합니다.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceJapaneseEraYearRanges`|일본어 달력 연대에 대 한 연도 범위 검사가 적용 되는지 여부를 제어 합니다. 연도 범위 검사를 적용 하 `false` 고 사용 하지 않도록 설정 하는 `true` (기본 동작) 자세한 내용은 [달력을 사용 하 여 작업](../../../../standard/datetime/working-with-calendars.md)합니다.|.NET Framework 4.6|
|`Switch.System.Globalization.EnforceLegacyJapaneseDateParsing`|구문 분석 작업에서 "1"만 일본 달력 연대의 첫 번째 연도로 인식 되는지 여부를 제어 합니다. "1"만 인식 `true` "1" 또는 Gannen (기본 동작)를 인식 하도록 `false` 합니다. 자세한 내용은 [달력을 사용 하 여 작업](../../../../standard/datetime/working-with-calendars.md)합니다.|.NET Framework 4.6|
|`Switch.System.Globalization.FormatJapaneseFirstYearAsANumber`|서식 지정 작업에서 일본 달력 연대의 첫 해를 "1"로 나타낼지 아니면 Gannen로 표시할지를 제어 합니다. 연대의 첫 해를 "1"로 서식 지정 하려면 `true` 합니다. Gannen로 서식 지정 `false` (기본 동작) 자세한 내용은 [달력을 사용 하 여 작업](../../../../standard/datetime/working-with-calendars.md)합니다.|.NET Framework 4.6|
|`Switch.System.Globalization.NoAsyncCurrentCulture`|비동기 작업이 호출 하는 스레드의 컨텍스트에서 전달 되지 않는지 여부를 제어 합니다. 자세한 내용은 [CurrentCulture And CurrentUICulture flow to tasks](../../../migration-guide/retargeting/4.5.2-4.6.md#currentculture-and-currentuiculture-flow-across-tasks)을 참조 하세요.|.NET Framework 4.6|
|`Switch.System.IdentityModel.`<br/>`DisableMultipleDNSEntriesInSANCertificate`|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=nameWithType> 메서드가 클레임 형식을 마지막 DNS 항목에만 일치 시 키 려 고 할지 여부를 제어 합니다. 자세한 내용은 [완화: X509CertificateClaimSet.FindClaims 메서드](../../../migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)를 참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.IdentityModel.`<br/>`EnableCachedEmptyDefaultAuthorizationContext`|변경할 수 있는 개체를 반환 하기 위해 AuthorizationContext를 허용할지 여부를 제어 합니다.|.NET Framework 4.6|
|`Switch.System.IO.BlockLongPaths`|`MAX_PATH` (260 자) 보다 긴 경로가 <xref:System.IO.PathTooLongException>를 throw 하는지 여부를 제어 합니다. 자세한 내용은 [긴 경로 지원](../../../migration-guide/retargeting/4.6.1-4.6.2.md#long-path-support)을 참조 하세요.|.NET Framework 4.6.2|
|`Switch.System.IO.Compression.`<br/>`DoNotUseNativeZipLibraryForDecompression`|네이티브 OS 루틴이 <xref:System.IO.Compression.DeflateStream> 클래스의 압축을 푸는 데 사용 되는지 여부를 제어 합니다. 네이티브 Api를 사용 하려면 `false` 합니다. <xref:System.IO.Compression.DeflateStream> 구현을 사용 하려면 `true` 합니다.|.NET Framework 4.7.2|
|`Switch.System.IO.Compression.ZipFile.`<br/>`UseBackslash`|는 슬래시 ("/")가 아닌 백슬래시 ("\\")를 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A?displayProperty=nameWithType> 속성의 경로 구분 기호로 사용 합니다. 자세한 내용은 [완화: ZipArchiveEntry 경로 구분 기호](../../../migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)를 참조 하세요.|.NET Framework 4.6.1|
|`Switch.System.IO.Ports.`<br/>`DoNotCatchSerialStreamThreadExceptions`|<xref:System.IO.Ports.SerialPort> 스트림으로 만든 백그라운드 스레드에서 throw 된 운영 체제 예외가 프로세스를 종료 하는지 여부를 제어 합니다.|.NET Framework 4.7.1|
|`Switch.System.IO.`<br/>`UseLegacyPathHandling`|레거시 경로 정규화를 사용 하 고 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> 메서드에서 URI 경로를 지원 하는지 여부를 제어 합니다. 자세한 내용은 [완화: 경로 정규화](../../../migration-guide/mitigation-path-normalization.md) 및 [완화: 경로 콜론 확인](../../../migration-guide/mitigation-path-colon-checks.md)을 참조 하세요.|.NET Framework 4.6.2|
|`Switch.System.`<br/>`MemberDescriptorEqualsReturnsFalseIfEquivalent`|같은지 테스트 한 개체의 <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=nameWithType> 속성과 두 번째 개체의 <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=nameWithType> 속성을 비교 하는지 여부를 제어 합니다. 자세한 내용은 [MemberDescriptor의 잘못 된 구현](../../../migration-guide/retargeting/4.6.1-4.6.2.md#incorrect-implementation-of-memberdescriptorequals)을 참조 하십시오. Equals.|.NET Framework 4.6.2|
 `Switch.System.Net.`<br/>`DontCheckCertificateEKUs`|EKU (인증서 확장 키 사용) OID (개체 식별자) 유효성 검사를 사용 하지 않도록 설정 합니다. EKU(향상된 키 사용) 확장은 키를 사용하는 애플리케이션을 나타내는 OID(개체 식별자)의 모음입니다.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchSendAuxRecord`|SCH_SEND_AUX_RECORD 사용을 사용 하지 않도록 설정 하 여 SSL/TLS (비스 트) 완화에 대해 TLS 1.0 브라우저 익스플로잇을 사용 하지 않도록 설정 합니다.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSchUseStrongCrypto`|<xref:System.Net.ServicePointManager?displayProperty=nameWithType> 및 <xref:System.Net.Security.SslStream?displayProperty=nameWithType> 클래스가 SSL 3.0 프로토콜을 사용할 수 있는지 여부를 제어 합니다. 자세한 내용은 [완화: TLS 프로토콜](../../../migration-guide/mitigation-tls-protocols.md)을 참조하십시오.|.NET Framework 4.6|
|`Switch.System.Net.`<br/>`DontEnableSystemDefaultTlsVersions`|SystemDefault TLS 버전을 Tls12, Tls11, Tls의 기본값으로 되돌립니다.|.NET Framework 4.7|
|`Switch.System.Net.`<br/>`DontEnableTlsAlerts`|SslStream TLS 서버 쪽 경고를 사용 하지 않도록 설정 합니다.|.NET Framework 4.7|
|`Switch.System.Runtime.InteropServices.`<br/>`DoNotMarshalOutByrefSafeArrayOnInvoke`|COM interop 이벤트에 대 한 ByRef SafeArray 매개 변수가 네이티브 코드 (`false`)로 마샬링 되는지 아니면 네이티브 코드로의 마샬링이 사용 하지 않도록 설정 되었는지 (`true`)를 제어 합니다.|.NET Framework 4.8|
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseECMAScriptV6EscapeControlCharacter` |[DataContractJsonSerializer](xref:System.Runtime.Serialization.Json.DataContractJsonSerializer) 가 ECMAScript V6 및 V8 표준을 기반으로 일부 제어 문자를 serialize 하는지 여부를 제어 합니다. 자세한 내용은 [완화: DataContractJsonSerializer로 제어 문자 serialization](../../../migration-guide/mitigation-serialization-control-characters.md)을 참조하세요.| .NET Framework 4.7 |
|`Switch.System.Runtime.Serialization.`<br/>`DoNotUseTimeZoneInfo`|<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>에서 여러 조정 또는 표준 시간대에 대 한 단일 조정을 지원 하는지 여부를 제어 합니다. `true`경우 <xref:System.TimeZoneInfo> 형식을 사용 하 여 날짜 및 시간 데이터를 직렬화 및 deserialize 합니다. 그렇지 않으면 여러 조정 규칙을 지원 하지 않는 <xref:System.TimeZone> 유형을 사용 합니다.|.NET Framework 4.6.2|
|`Switch.System.Runtime.Serialization.UseNewMaxArraySize`|개체 serialization 및 deserialization 중 <xref:System.Runtime.Serialization.ObjectManager?displayProperty=nameWithType>에서 더 큰 배열 크기를 사용할지 여부를 제어 합니다. 이 스위치를 `true`으로 설정 하 여 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>같은 형식으로 많은 개체 그래프의 serialization 및 deserialization 성능을 향상 시킬 수 있습니다. |.NET Framework 4.7.2|
|`Switch.System.Security.ClaimsIdentity.`<br/>`SetActorAsReferenceWhenCopyingClaimsIdentity`|<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=nameWithType> 생성자가 새 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=nameWithType> 속성을 기존 개체 참조로 설정 하는지 여부를 제어 합니다. 자세한 내용은 [완화: ClaimsIdentity 생성자](../../../migration-guide/retargeting/4.6.1-4.6.2.md)를 참조하세요.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`AesCryptoServiceProvider.DontCorrectlyResetDecryptor`|<xref:System.Security.Cryptography.AesCryptoServiceProvider> 암호 해독기를 다시 사용 하려고 하면 <xref:System.Security.Cryptography.CryptographicException>throw 되는지 여부를 제어 합니다. 자세한 내용은 [AesCryptoServiceProvider 암호 해독기에서 다시 사용할 수 있는 변환 제공](../../../migration-guide/retargeting/4.6.1-4.6.2.md#aescryptoserviceprovider-decryptor-provides-a-reusable-transform)을 참조 하세요.|.NET Framework 4.6.2|
|`Switch.System.Security.Cryptography.`<br/>`DoNotAddrOfCspParentWindowHandle`|[System.security.cryptography.cspparameters.parentwindowhandle](xref:System.Security.Cryptography.CspParameters.ParentWindowHandle) 속성의 값이 창 핸들의 메모리 위치를 나타내는 [IntPtr](xref:System.IntPtr) 또는 창 핸들 (HWND) 인지 여부를 제어 합니다. 자세한 내용은 [완화: CspParameters.ParentWindowHandle에 HWND 필요](../../../migration-guide/retargeting/4.6.2-4.7.md#cspparametersparentwindowhandle-now-expects-hwnd-value)를 참조하세요. |.NET Framework 4.7|
|`Switch.System.Security.Cryptography.`<br/>`UseLegacyFipsThrow`|FIPS 모드에서 관리 되는 암호화 클래스를 사용 하 여 <xref:System.Security.Cryptography.CryptographicException> (`true`)를 throw 하거나 시스템 라이브러리 (`false`) 구현에 의존 하는지 여부를 제어 합니다.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Pkcs.`<br/>`UseInsecureHashAlgorithms`|일부 SignedCMS 작업에 대 한 기본값이 SHA1 또는 s h a 1 인지 여부를 결정 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.Security.Cryptography.X509Certificates.`<br/>`ECDsaCertificateExtensions.UseLegacyPublicKeyReader`|<xref:System.Security.Cryptography.X509Certificates.ECDsaCertificateExtensions.GetECDsaPublicKey%2A?displayProperty=nameWithType> 메서드가 운영 체제에서 지원 되는 모든 명명 된 곡선 (`false`)을 올바르게 처리할지 또는 레거시 동작으로 되돌리는 지를 제어 합니다.|.NET Framework 4.8|
|`Switch.System.Security.Cryptography.Xml.`<br/>`UseInsecureHashAlgorithms`|일부 기능을 수행 하는 Xml 작업의 기본값이 SHA1 또는 s h a 1 인지 여부를 결정 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`AllowUnsignedToHeader`|`TransportWithMessageCredential` 보안 모드에서 부호 없는 "to" 헤더가 있는 메시지를 허용 하는지 여부를 확인 합니다. 이 스위치는 옵트인 스위치입니다. 자세한 내용은 [.NET Framework 4.6.1의 런타임 변경 내용](../../../migration-guide/runtime/4.5.2-4.6.1.md#windows-communication-foundation-wcf)을 참조 하세요.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableAddressHeaderCollectionValidation`>|요소 중 하나가 `null`경우 <xref:System.ServiceModel.Channels.AddressHeaderCollection.%23ctor(System.Collections.Generic.IEnumerable{System.ServiceModel.Channels.AddressHeader})> 생성자가 <xref:System.ArgumentException>를 throw 하는지 여부를 제어 합니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br />`DisableCngCertificates`|CSG 키 저장소 공급자와 함께 X509 인증서를 사용 하려고 하면 예외가 throw 되는지 여부를 결정 합니다. 자세한 내용은 [WCF 전송 보안에서 CNG를 사용 하 여 저장 된 인증서 지원](../../../migration-guide/retargeting/4.6.1-4.6.2.md#wcf-transport-security-supports-certificates-stored-using-cng)을 참조 하세요.|.NET Framework 4.6.1|
|`Switch.System.ServiceModel.`<br/>`DisableExplicitConnectionCloseHeader`|자체 호스팅 서비스에서 HTTP 전송을 사용 하는 경우이 값을 `true`로 설정 하면 WCF에서 요청에 대 한 응답 헤더에 `Connection: close` 헤더를 추가 하는 응용 프로그램을 무시 합니다. 이 값을 `false`로 설정 하면 응답 헤더에 `Connection: close` 헤더를 추가할 수 있으며,이로 인해 응답이 전송 된 후에 요청 소켓이 닫힙니다.|.NET Framework 4.6|
|`Switch.System.ServiceModel.`<br/>`DisableOperationContextAsyncFlow`|재진입용 서비스의 인스턴스를 한 번에 하나의 실행 스레드로 제한 하 여 발생 하는 교착 상태를 처리 합니다.|.NET Framework 4.6.2|
|`Switch.System.ServiceModel.`<br/>`DisableUsingServicePointManagerSecurityProtocols`|`Switch.System.Net.DontEnableSchUseStrongCrypto`와 함께 WCF 메시지 보안에서 TLS 1.1 및 TLS 1.2을 사용 하는지 여부를 결정 합니다.|.NET Framework 4.7 |
|`Switch.System.ServiceModel.`<br/>`DontEnableSystemDefaultTlsVersions`|`false` 값은 운영 체제에서 프로토콜을 선택할 수 있도록 기본 구성을 설정 합니다. `true` 값은 기본값을 사용 가능한 가장 높은 프로토콜로 설정 합니다. (이전 프레임 워크 버전의 서비스 분기 에서도 사용할 수 있음)|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InMsmqEncryptionAlgorithm`|WCF의 MSMQ 메시지에 대 한 기본 메시지 서명 알고리즘이 SHA1 또는 s h a 1 인지 여부를 결정 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.`<br/>`UseSha1InPipeConnectionGetHashAlgorithm`|WCF가 SHA1 또는 SHA256 해시를 사용 하 여 명명 된 파이프에 대 한 무작위 이름을 생성 하는지 여부를 제어 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.1|
|`Switch.System.ServiceModel.Internals`<br/>`IncludeNullExceptionMessageInETWTrace`|예외 메시지가 null 인 경우 [NullReferenceException](xref:System.NullReferenceException) 을 throw 할지 여부를 제어 합니다.|.NET Framework 4.7|
|`Switch.System.ServiceProcess.`<br/>`DontThrowExceptionsOnStart`|서비스 시작 시 throw 된 예외가 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> 메서드의 호출자에 게 전파 되는지 여부를 제어 합니다.|.NET Framework 4.7.1|
|`Switch.System.Threading.UseNetCoreTimer`|<xref:System.Threading.Timer> 인스턴스가 높은 규모의 환경에 대 한 성능 향상을 활용할 지 여부를 제어 합니다. `true`경우 성능을 향상 시킬 수 있습니다. `false` (기본값) 이면 해당 값을 사용할 수 없습니다.|.NET Framework 4.8|
|`Switch.System.Uri.`<br/>`DontEnableStrictRFC3986ReservedCharacterSets`|간혹 디코딩되는 특정 백분율 인코딩된 문자가 이제 일관 되 게 왼쪽으로 인코딩 되는지 여부를 결정 합니다. `true`경우 디코딩됩니다. 그렇지 않으면 `false`합니다.|.NET Framework 4.7.2|
|`Switch.System.Uri.`<br/>`DontKeepUnicodeBidiFormattingCharacters`|Uri에서 유니코드 양방향 문자를 처리 하는 방법을 결정 합니다. Uri에서 제거 하려면 `true` 합니다. `false` 하 여 유지 하 고 비율을 인코딩합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Controls.Grid.`<br/>`StarDefinitionsCanExceedAvailableSpace` |\*열에 공간을 할당할 때 Windows Presentation Foundation 이전 알고리즘 (`true`) 또는 새 알고리즘 (`false`)을 적용할지 여부를 결정 합니다. 자세한 내용은 [완화: Grid 컨트롤의 별 열 공간 할당](../../../migration-guide/retargeting/4.6.2-4.7.md#wpf-grid-allocation-of-space-to-star-columns)을 참조하세요. |.NET Framework 4.7 |
|`Switch.System.Windows.Controls.TabControl.`<br/>`SelectionPropertiesCanLagBehindSelectionChangedEvent`|선택 변경 이벤트를 발생 시키기 전에 선택기 또는 탭 컨트롤이 항상 선택 된 값 속성의 값을 업데이트 하는지 여부를 제어 합니다.|.NET Framework 4.7.1|
|`Switch.System.Windows.Controls.Text.`<br/>`UseAdornerForTextboxSelectionRendering`|폐색 텍스트 (`false`)를 방지 하기 위해 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.PasswordBox> 컨트롤에 대해 비 표시기 기반 선택 렌더링을 사용할 수 있는지 또는 표시기 계층 (`true`) 에서만 텍스트가 렌더링 되는지 여부를 결정 합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Data.Binding.`<br/>`IListIndexerHidesCustomIndexer`|<xref:System.Windows.Data.Binding?displayProperty=nameWithType> 클래스에서 사용자 지정 IList 인덱서가 잘못 사용 (`true`) 되는지 또는 올바르게 사용 되는지 (`false`)를 제어 합니다.|.NET Framework 4.8|
|`Switch.System.Windows.DoNotScaleForDpiChanges`|DPI 변경이 시스템 단위 (`false`값) 또는 모니터 단위 기준 (`true`값)에서 발생 하는지 여부를 확인 합니다.|.NET Framework 4.6.2|
|`Switch.System.Windows.`<br/>`DoNotUsePresentationDpiCapabilityTier2OrGreater`|모니터 당 인식 모드로 WPF를 실행할 때 <xref:System.Windows.Interop.HwndHost?displayProperty=nameWithType>에서 컨트롤의 크기를 조정할 수 있는지 여부를 제어 합니다 (`true`) 또는 사용 (`false`).|.NET Framework 4.8|
|`Switch.System.Windows.Forms.`<br/>`DomainUpDown.UseLegacyScrolling`|컨트롤 텍스트가 있을 때 개발자가 특별히 <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 작업을 처리 해야 하는지 여부를 결정 합니다. <xref:System.Windows.Forms.DomainUpDown.UpButton> 동작을 처리 `true` <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> 작업이 제대로 동기화 `false` 합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.`<br />`DontSupportReentrantFilterMessage`|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드가 호출 될 때 예외를 throw 하지 않고 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 메시지를 안전 하 게 필터링 할 수 있도록 하는 코드를 Opts 합니다. 자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](../../../migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하십시오.|.NET Framework 4.6.1|
|`Switch.System.Windows.Forms.`<br/>`UseLegacyContextMenuStripSourceControlValue`|사용자가 중첩 된 <xref:System.Windows.Forms.ToolStripMenuItem> 컨트롤에서 메뉴를 열 때 <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> 속성이 소스 제어를 반환 하는지 여부를 확인 합니다. 레거시 동작을 `true` `null`를 반환 합니다. 원본 제어를 반환 하려면 `false` 합니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Forms.UseLegacyToolTipDisplay`|도구 설명 호출 지원을 사용 하지 않도록 설정 (`true`) 하거나 사용 (`false`) 할지 여부를 제어 합니다. 도구 설명 호출 지원을 사용 하려면 `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`및 `Switch.UseLegacyAccessibilityFeatures.3` 모두 사용 하지 않도록 설정 된 레거시 접근성 기능이 필요 합니다 (`false`로 설정 됨).|.NET Framework 4.8|
|`Switch.System.Windows.Input.Stylus.`<br/>`EnablePointerSupport`|WPF 응용 프로그램에서 선택적 `WM_POINTER`기반 터치/스타일러스 스택을 사용 하도록 설정할지 여부를 결정 합니다. 자세한 내용은 [완화: 포인터 기반 터치 및 스타일러스 지원](../../../migration-guide/mitigation-pointer-based-touch-and-stylus-support.md) 을 참조 하세요.|.NET Framework 4.7|
|`Switch.System.Windows.Markup.`<br/>`DoNotUseSha256ForMarkupCompilerChecksumAlgorithm`|체크섬에 사용 되는 기본 해시 알고리즘이 SHA256 (`false`) 또는 SHA1 (`true`) 인지 여부를 확인 합니다.<br>SHA1 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.7.2|
|`Switch.System.Windows.Media.ImageSourceConverter.`<br/>`OverrideExceptionWithNullReferenceException`|예외 (예: [system.io.directorynotfoundexception>](xref:System.IO.DirectoryNotFoundException) 또는 [system.io.filenotfoundexception](xref:System.IO.FileNotFoundException))의 원인을 보다 구체적으로 지정 하는 예외 대신 레거시 [NullReferenceException](xref:System.NullReferenceException) throw 되는지 여부를 제어 합니다. [NullReferenceException](xref:System.NullReferenceException)처리에 의존 하는 코드에서 사용 하기 위한 것입니다. | .NET Framework 4.7 |
|`Switch.System.Workflow.ComponentModel.`<br/>`UseLegacyHashForXomlFileChecksum`|워크플로 프로젝트 빌드에서 XOML 파일의 체크섬 해시가 MD5 알고리즘 (`true`)을 사용 하는지 또는 4.8 .NET Framework에서 기본값으로 도입 된 SHA256 알고리즘을 사용 하는지 여부를 제어 합니다.<br>MD5 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForSqlTrackingCacheKey`|SqlTrackingService의 체크섬 해시가 캐시 된 문자열에 대해 MD5 알고리즘 (`true`)을 사용 하는지 여부 또는 4.8 .NET Framework에서 기본값으로 도입 된 SHA256 알고리즘을 사용 하는지 여부를 제어 합니다.<br>MD5 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.System.Workflow.Runtime.`<br/>`UseLegacyHashForWorkflowDefinitionDispenserCacheKey`|워크플로 런타임에의 한 체크섬 해시가 캐시 된 워크플로 정의에 MD5 알고리즘 (`true`)을 사용 하는지 여부 또는 4.8 .NET Framework에서 기본값으로 도입 된 SHA256 알고리즘을 사용 하는지 여부를 제어 합니다.<br>MD5 관련 충돌 문제로 인해 SHA256을 사용하는 것이 좋습니다.|.NET Framework 4.8|
|`Switch.UseLegacyAccessibilityFeatures`|.NET Framework 4.7.1부터 사용할 수 있는 내게 필요한 옵션 기능을 사용 하거나 사용 하지 않도록 설정할지 여부를 제어 합니다. | .NET Framework 4.7.1 |
|`Switch.UseLegacyAccessibilityFeatures.2`|.NET Framework 4.7.2에서 사용할 수 있는 내게 필요한 옵션 기능을 사용할 수 있는지 여부를 제어 합니다 (`false`) 또는 사용 안 함 (`true`). `true`경우 .NET Framework 4.7.1 접근성 기능을 사용 하려면 `Switch.UseLegacyAccessibilityFeatures` `true` 해야 합니다.|.NET Framework 4.7.2|
|`Switch.UseLegacyAccessibilityFeatures.3`|.NET Framework 4.8에 도입 된 내게 필요한 옵션 기능이 사용 (`false`) 또는 사용 안 함 (`true`) 인지 여부를 제어 합니다. `true`경우 `Switch.UseLegacyAccessibilityFeatures` 및 `Switch.UseLegacyAccessibilityFeatures.2`도 `true`해야 합니다.|.NET Framework 4.8|
|`Switch.UseLegacyToolTipDisplay`|사용자가 WPF 컨트롤 위로 마우스 커서를 이동 하거나 (`true`) 키보드 포커스와 키보드 바로 가기 키 (`false`기본 동작)를 사용 하 여 도구 설명을 표시할지 여부를 제어 합니다. .NET Framework 4.8에서 실행 되지만 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램의 경우 키보드 포커스 및 바로 가기 키 지원을 모두 사용 하려면 `Switch.UseLegacyAccessibilityFeatures`, `Switch.UseLegacyAccessibilityFeatures.2`및 `Switch.UseLegacyAccessibilityFeatures.3` 모두 `false`로 설정 해야 합니다.|.NET Framework 4.8|
|`Switch.System.Xml.`<br />`IgnoreEmptyKeySequences`|복합 키의 빈 키 시퀀스가 XSD 스키마 유효성 검사에서 무시 되는지 여부를 제어 합니다. 자세한 내용은 [완화: XML 스키마 유효성 검사](../../../migration-guide/mitigation-xml-schema-validation.md)를 참조 하세요.|.NET Framework 4.6|

> [!NOTE]
> `AppContextSwitchOverrides` 요소를 응용 프로그램 구성 파일에 추가 하는 대신 `static` (의 C#경우) 또는 `Shared` (Visual Basic) <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출 하 여 스위치를 프로그래밍 방식으로 설정할 수도 있습니다.

 라이브러리 개발자는 호출자가 이후 버전의 라이브러리에 도입 된 변경 된 기능을 옵트아웃 (opt out) 할 수 있도록 사용자 지정 스위치를 정의할 수도 있습니다. 자세한 내용은 <xref:System.AppContext> 클래스 참조하세요.

## <a name="switches-in-aspnet-applications"></a>ASP.NET 응용 프로그램의 스위치

[\<](../appsettings/add-element-for-appsettings.md) 요소를 추가 하 여 web.config 파일의 [\<appSettings >](../appsettings/index.md) 섹션에 호환성 설정을 사용 하도록 ASP.NET 응용 프로그램을 구성할 수 있습니다.

다음 예제에서는 `<add>` 요소를 사용 하 여 web.config 파일의 `<appSettings>` 섹션에 두 설정을 추가 합니다.

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="example"></a>예

 다음 예제에서는 `AppContextSwitchOverrides` 요소를 사용 하 여 비동기 메서드 호출에서 문화권이 스레드 간에 흐르는 것을 방지 하는 단일 응용 프로그램 호환성 스위치 `Switch.System.Globalization.NoAsyncCurrentCulture`를 정의 합니다.

```xml
<configuration>
   <runtime>
      <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />
   </runtime>
</configuration>
```

 다음 예제에서는 `AppContextSwitchOverrides` 요소를 사용 하 여 `Switch.System.Globalization.NoAsyncCurrentCulture` 및 `Switch.System.IO.BlockLongPaths`의 두 가지 응용 프로그램 호환성 스위치를 정의 합니다. 세미콜론은 두 개의 이름/값 쌍을 구분 합니다.

```xml
<configuration>
    <runtime>
       <AppContextSwitchOverrides
          value="Switch.System.Globalization.NoAsyncCurrentCulture=true;Switch.System.IO.BlockLongPaths=true" />
    </runtime>
</configuration>
```

## <a name="see-also"></a>참조

- <xref:System.AppContext?displayProperty=nameWithType>
- [\<runtime > 요소](runtime-element.md)
- [\<configuration> 요소](../configuration-element.md)
