---
title: 메서드 런타임 이벤트
description: CLR 메서드 이벤트, CLR 메서드 표식 또는 CLR 메서드 자세한 이벤트, MethodJittingStarted와 같은 메서드와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
helpviewer_keywords:
- Method events (CoreCLR)
- ETW, EventPipe, LTTng method events (CoreCLR)
ms.openlocfilehash: f9d08efa420670cf7a8c863f115ff270998f2dca
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594040"
---
# <a name="net-runtime-method-events"></a>.NET 런타임 메서드 이벤트

이들 이벤트는 메서드와 관련된 정보를 수집합니다. 이들 이벤트의 페이로드는 기호 확인을 위해 필요합니다. 또한 이러한 이벤트는 로드 되 고 언로드된 메서드와 같은 유용한 정보를 제공 합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

모든 메서드 이벤트에는 "정보 제공(4)" 수준이 있습니다. 모든 메서드 자세한 정보 표시 이벤트에는 "자세한 정보 표시(5)" 수준이 있습니다.

모든 메서드 이벤트는 런타임 공급자에서 `JITKeyword` (0x10) 키워드 또는 `NGenKeyword` (0x20) 키워드에 의해 발생하거나 런다운 공급자에서 `JitRundownKeyword` (0x10) 또는 `NGENRundownKeyword` (0x20)에 의해 발생합니다.

이러한 이벤트의 V2 버전에는 ReJITID가 포함 되며, V1 버전은 그렇지 않습니다.

## <a name="methodload_v1-event"></a>MethodLoad_V1 이벤트

다음 표에서는 이벤트 정보를 보여 줍니다.

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodLoad_V1`|141|메서드가 JIT(Just-In-Time) 로드되거나 NGEN 이미지가 로드될 때 발생합니다. 동적 및 제네릭 메서드는 메서드 로드에 대해 이 버전을 사용하지 않습니다. JIT 도우미는 이 버전을 사용하지 않습니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) 런타임 공급자|정보(4)|
|`NGenKeyword` (0x20) 런타임 공급자|정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|메서드의 시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드의 크기입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).<br /><br /> 0x8: 도우미 메서드.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodload_v2-event"></a>MethodLoad_V2 이벤트

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`MethodLoad_V2`|141|메서드가 JIT(Just-In-Time) 로드되거나 NGEN 이미지가 로드될 때 발생합니다. 동적 및 제네릭 메서드는 메서드 로드에 대해 이 버전을 사용하지 않습니다. JIT 도우미는 이 버전을 사용하지 않습니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) 런타임 공급자|정보(4)|
|`NGenKeyword` (0x20) 런타임 공급자|정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|메서드의 시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드의 크기입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).<br /><br /> 0x8: 도우미 메서드.|
|`ReJITID`|`win:UInt64`|메서드의 ReJIT ID입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodunload_v1-event"></a>MethodUnLoad_V1 이벤트

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`MethodUnLoad_V1`|142|모듈이 언로드되거나 애플리케이션 도메인이 삭제될 때 발생합니다. 동적 메서드는 메서드 언로드에 대해 이 버전을 사용하지 않습니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)|정보(4)|
|`NGenKeyword` 0x20|정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|메서드의 시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드의 크기입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).<br /><br /> 0x8: 도우미 메서드.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodunload_v2-event"></a>MethodUnLoad_V2 이벤트

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`MethodUnLoad_V2`|142|모듈이 언로드되거나 애플리케이션 도메인이 삭제될 때 발생합니다. 동적 메서드는 메서드 언로드에 대해 이 버전을 사용하지 않습니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10)|정보(4)|
|`NGenKeyword` 0x20|정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드에 대한 이 필드는 메서드의 시작 주소로 설정됩니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|메서드의 시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드의 크기입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 코드 메서드(이외의 경우 NGEN 네이티브 이미지 코드).<br /><br /> 0x8: 도우미 메서드.|
|`ReJITID`|`win:UInt64`|메서드의 ReJIT ID입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="r2rgetentrypoint-event"></a>R2RGetEntryPoint 이벤트

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`R2RGetEntryPoint`|159|R2R entry point 조회가 종료 될 때 발생 합니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |정보(4)|
|`NGenKeyword` 0x20 |정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|R2R 메서드의 고유 식별자입니다.|
|`MethodNamespace`|`win:UnicodeString`|조회 되는 메서드의 네임 스페이스입니다.|
|`MethodName`|`win:UnicodeString`|조회 되는 메서드의 이름입니다.|
|`MethodSignature`|`win:UnicodeString`|메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).|
|`EntryPoint`|`win:UInt64`|R2R 메서드의 진입점에 대 한 포인터입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="r2rgetentrypointstart-event"></a>R2RGetEntryPointStart 이벤트

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`R2RGetEntryPointStart`|160|R2R 진입점 조회가 시작 될 때 발생 합니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |정보(4)|
|`NGenKeyword` 0x20 |정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|R2R 메서드의 고유 식별자입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodloadverbose_v1-event"></a>MethodLoadVerbose_V1 이벤트

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|메서드가 JIT 로드되거나 NGEN 이미지가 로드될 때 발생합니다. 동적 및 제네릭 메서드는 항상 메서드 로드에 대해 이 버전을 사용합니다. JIT 도우미는 항상 이 버전을 사용합니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |정보(4)|
|`NGenKeyword` 0x20 |정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드 길이입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)<br /><br /> 0x8: 도우미 메서드.|
|`MethodNameSpace`|`win:UnicodeString`|메서드와 연결된 전체 네임스페이스 이름입니다.|
|`MethodName`|`win:UnicodeString`|메서드와 연결된 전체 클래스 이름입니다.|
|`MethodSignature`|`win:UnicodeString`|메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodloadverbose_v2-event"></a>MethodLoadVerbose_V2 이벤트

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodLoadVerbose_V1`|143|메서드가 JIT 로드되거나 NGEN 이미지가 로드될 때 발생합니다. 동적 및 제네릭 메서드는 항상 메서드 로드에 대해 이 버전을 사용합니다. JIT 도우미는 항상 이 버전을 사용합니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |정보(4)|
|`NGenKeyword` 0x20 |정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드 길이입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)<br /><br /> 0x8: 도우미 메서드.|
|`MethodNameSpace`|`win:UnicodeString`|메서드와 연결된 전체 네임스페이스 이름입니다.|
|`MethodName`|`win:UnicodeString`|메서드와 연결된 전체 클래스 이름입니다.|
|`MethodSignature`|`win:UnicodeString`|메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).|
|`ReJITID`|`win:UInt64`|메서드의 ReJIT ID입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodunloadverbose_v1-event"></a>MethodUnLoadVerbose_V1 이벤트

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V1`|144|동적 메서드가 삭제되거나, 모듈이 언로드되거나, 애플리케이션 도메인이 삭제될 때 발생합니다. 동적 메서드는 항상 메서드 언로드에 대해 이 버전을 사용합니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |정보(4)|
|`NGenKeyword` 0x20 |정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드 길이입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)<br /><br /> 0x8: 도우미 메서드.|
|`MethodNameSpace`|`win:UnicodeString`|메서드와 연결된 전체 네임스페이스 이름입니다.|
|`MethodName`|`win:UnicodeString`|메서드와 연결된 전체 클래스 이름입니다.|
|`MethodSignature`|`win:UnicodeString`|메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodunloadverbose_v2-event"></a>MethodUnLoadVerbose_V2 이벤트

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodUnLoadVerbose_V2`|144|동적 메서드가 삭제되거나, 모듈이 언로드되거나, 애플리케이션 도메인이 삭제될 때 발생합니다. 동적 메서드는 항상 메서드 언로드에 대해 이 버전을 사용합니다.|

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |정보(4)|
|`NGenKeyword` 0x20 |정보(4)|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다. JIT 도우미 메서드의 경우 메서드의 시작 주소로 설정합니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다(JIT 도우미의 경우 0).|
|`MethodStartAddress`|`win:UInt64`|시작 주소입니다.|
|`MethodSize`|`win:UInt32`|메서드 길이입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodFlags`|`win:UInt32`|0x1: 동적 메서드.<br /><br /> 0x2: 제네릭 메서드.<br /><br /> 0x4: JIT 컴파일된 메서드(이외의 경우 NGen.exe에서 생성됨)<br /><br /> 0x8: 도우미 메서드.|
|`MethodNameSpace`|`win:UnicodeString`|메서드와 연결된 전체 네임스페이스 이름입니다.|
|`MethodName`|`win:UnicodeString`|메서드와 연결된 전체 클래스 이름입니다.|
|`MethodSignature`|`win:UnicodeString`|메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).|
|`ReJITID`|`win:UInt64`|메서드의 ReJIT ID입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodjittingstarted_v1-event"></a>MethodJittingStarted_V1 이벤트

다음 표에서는 키워드와 수준을 보여 줍니다.

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITKeyword` (0x10) |자세한 정보 표시(5)|
|`NGenKeyword` 0x20 |자세한 정보 표시(5)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodJittingStarted_V1`|145|메서드가 JIT로 컴파일되는 동안 발생합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다.|
|`ModuleID`|`win:UInt64`|이 메서드가 속한 모듈의 식별자입니다.|
|`MethodToken`|`win:UInt32`|동적 메서드 및 JIT 도우미의 경우 0입니다.|
|`MethodILSize`|`win:UInt32`|JIT로 컴파일되는 메서드에 대 한 CIL (공용 중간 언어)의 크기입니다.|
|`MethodNameSpace`|`win:UnicodeString`|메서드와 연결된 전체 클래스 이름입니다.|
|`MethodName`|`win:UnicodeString`|메서드의 이름입니다.|
|`MethodSignature`|`win:UnicodeString`|메서드의 서명입니다(쉼표로 구분된 형식 이름 목록).|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodjitinliningsucceeded-event"></a>MethodJitInliningSucceeded 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |자세한 정보 표시(5)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodJitInliningSucceeded`|185|JIT 컴파일러에 의해 메서드가 성공적으로 인라인 될 때 발생 합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|컴파일되는 메서드의 네임 스페이스입니다.|
|`MethodBeingCompiledName`|`win:UnicodeString`|컴파일되는 메서드의 이름입니다.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`InlinerNamespace`|`win:UnicodeString`|인라인 처리자 ("parent") 메서드의 네임 스페이스입니다.|
|`InlinerName`|`win:UnicodeString`|인라인 처리자 ("parent") 메서드의 이름입니다.|
|`InlinerNameSignature`|`win:UnicodeString`|인라인 처리자 ("parent") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`InlineeNamespace`|`win:UnicodeString`|인라인 대상 ("child") 메서드의 네임 스페이스입니다.|
|`InlineeName`|`win:UnicodeString`|인라인 대상 ("child") 메서드의 이름입니다.|
|`InlineeNameSignature`|`win:UnicodeString`|인라인 대상 ("child") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodjitinliningfailed-event"></a>MethodJitInliningFailed 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |자세한 정보 표시(5)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodJitInliningFailed`|192|JIT 컴파일러에서 메서드를 인라이닝 하지 못할 때 발생 합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|컴파일되는 메서드의 네임 스페이스입니다.|
|`MethodBeingCompiledName`|`win:UnicodeString`|컴파일되는 메서드의 이름입니다.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`InlinerNamespace`|`win:UnicodeString`|인라인 처리자 ("parent") 메서드의 네임 스페이스입니다.|
|`InlinerName`|`win:UnicodeString`|인라인 처리자 ("parent") 메서드의 이름입니다.|
|`InlinerNameSignature`|`win:UnicodeString`|인라인 처리자 ("parent") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`InlineeNamespace`|`win:UnicodeString`|인라인 대상 ("child") 메서드의 네임 스페이스입니다.|
|`InlineeName`|`win:UnicodeString`|인라인 대상 ("child") 메서드의 이름입니다.|
|`InlineeNameSignature`|`win:UnicodeString`|인라인 대상 ("child") 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`FailAlways`|`win:Boolean`|메서드가 not inlinable로 표시 되는지 여부를 나타냅니다.|
|`FailReason`|`win:UnicodeString`|이유를 인라이닝 하지 못했습니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodjittailcallsucceeded-event"></a>MethodJitTailCallSucceeded 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |자세한 정보 표시(5)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodJitTailCallSucceeded`|192|메서드가 성공적으로 호출 될 수 있는 경우 JIT 컴파일러에 의해 발생 합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|컴파일되는 메서드의 네임 스페이스입니다.|
|`MethodBeingCompiledName`|`win:UnicodeString`|컴파일되는 메서드의 이름입니다.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`CallerNamespace`|`win:UnicodeString`|호출자 메서드의 네임 스페이스입니다.|
|`CallerName`|`win:UnicodeString`|호출자 메서드의 이름입니다.|
|`CallerNameSignature`|`win:UnicodeString`|호출자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`CalleeNamespace`|`win:UnicodeString`|호출 수신자 메서드의 네임 스페이스입니다.|
|`CalleeName`|`win:UnicodeString`|호출 수신자 메서드의 이름입니다.|
|`CalleeNameSignature`|`win:UnicodeString`|호출 수신자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`TailPrefix`|`win:Boolean`|Tail 접두사 명령 인지 여부를 나타냅니다.|
|`TailCallType`|`win:UInt32`|마무리 호출의 형식입니다.<br/><br/>0: 마무리 호출 최적화 (에필로그 + jmp)<br/><br/>1: 재귀적 마무리 호출 (메서드 마무리 자체 호출)<br/><br/>2: 도우미 지원 마무리 호출|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodjittailcallfailed-event"></a>MethodJitTailCallFailed 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JITTracingKeyword` 0x1000 |자세한 정보 표시(5)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`MethodJitTailCallFailed`|191|메서드가 tail. 호출에 실패 한 경우 JIT 컴파일러에 의해 발생 합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodBeingCompiledNamespace`|`win:UnicodeString`|컴파일되는 메서드의 네임 스페이스입니다.|
|`MethodBeingCompiledName`|`win:UnicodeString`|컴파일되는 메서드의 이름입니다.|
|`MethodBeingCompiledNameSignature`|`win:UnicodeString`|컴파일되는 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`CallerNamespace`|`win:UnicodeString`|호출자 메서드의 네임 스페이스입니다.|
|`CallerNam`e|`win:UnicodeString`|호출자 메서드의 이름입니다.|
|`CallerNameSignature`|`win:UnicodeString`|호출자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`CalleeNamespace`|`win:UnicodeString`|호출 수신자 메서드의 네임 스페이스입니다.|
|`CalleeName`|`win:UnicodeString`|호출 수신자 메서드의 이름입니다.|
|`CalleeNameSignature`|`win:UnicodeString`|호출 수신자 메서드의 서명입니다 (쉼표로 구분 된 형식 이름 목록).|
|`TailPrefix`|`win:Boolean`|Tail 접두사 명령 인지 여부를 나타냅니다.|
|`FailReason`|`win:UnicodeString`|설명 tail 호출이 실패 했습니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="methodiltonativemap-event"></a>MethodILToNativeMap 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|
|`JittedMethodILToNativeMapKeyword` (0x20000) |자세한 정보 표시(5)|

|이벤트|이벤트 ID|Description|
|----------------|---------------|-----------------|
|`MethodILToNativeMap`|190|JIT 컴파일된 메서드에 대 한 IL-네이티브 맵 이벤트를 매핑합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`MethodID`|`win:UInt64`|메서드의 고유 식별자입니다.|
|`ReJITID`|`win:UInt64`|메서드의 ReJIT ID입니다.|
|`MethodExtent`|`win:UInt8`|Jit 컴파일된 메서드의 익스텐트입니다.|
|`CountOfMapEntries`|`win:UInt8`|맵 항목 수|
|`ILOffsets`|`win:UInt32`|IL 오프셋입니다.|
|`NativeOffsets`|`win:UInt32`|네이티브 코드 오프셋입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|
