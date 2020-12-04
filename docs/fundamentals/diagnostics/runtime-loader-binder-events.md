---
title: 로더 및 바인더 런타임 이벤트
description: 어셈블리 로더 및 바인더에 대 한 정보를 수집 하는 로더 및 바인더 ETW 이벤트와 관련 된 진단 정보를 수집 하는 .NET 런타임 이벤트를 참조 하세요.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- Assembly Loader events (CoreCLR)
- Assembly Binder events (CoreCLR)
- ETW, EventPipe, LTTng assembly loader and binder events (CoreCLR)
ms.openlocfilehash: 2284c580482f6b93a77f44649225ff7e5485666a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594111"
---
# <a name="net-runtime-loader-and-binder-events"></a>.NET 런타임 로더 및 바인더 이벤트

이러한 이벤트는 어셈블리 및 모듈 로드 및 언로드와 관련 된 정보를 수집 합니다. 진단 목적으로 이러한 이벤트를 사용 하는 방법에 대 한 자세한 내용은 [.net 응용 프로그램 로깅 및 추적](../../core/diagnostics/logging-tracing.md) 을 참조 하세요.

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`DomainModuleLoad_V1`|151|애플리케이션 도메인에 대한 모듈이 로드될 때 발생합니다.|

## <a name="moduleload_v2-event"></a>ModuleLoad_V2 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ModuleLoad_V2`|152|프로세스 수명 중에 모듈이 로드될 때 발생합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|모듈의 고유 ID입니다.|
|`AssemblyID`|`win:UInt64`|이 모듈이 있는 어셈블리의 ID입니다.|
|`ModuleFlags`|`win:UInt32`|0x1: 도메인 중립 모듈.<br /><br /> 0x2: 모듈에 네이티브 이미지 있음.<br /><br /> 0x4: 동적 모듈.<br /><br /> 0x8: 매니페스트 모듈.|
|`Reserved1`|`win:UInt32`|예약된 필드입니다.|
|`ModuleILPath`|`win:UnicodeString`|모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.|
|`ModuleNativePath`|`win:UnicodeString`|있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|
|`ManagedPdbSignature`|`win:GUID`|이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.|
|`ManagedPdbAge`|`win:UInt32`|이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다. 경우에 따라 파일 이름일 수도 있습니다.|
|`NativePdbSignature`|`win:GUID`|이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).|
|`NativePdbAge`|`win:UInt32`|이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).|
|`NativePdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우). 경우에 따라 파일 이름일 수도 있습니다.|

## <a name="moduleunload_v2-event"></a>ModuleUnload_V2 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ModuleUnload_V2`|153|프로세스 수명 중에 모듈이 언로드될 때 발생합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|모듈의 고유 ID입니다.|
|`AssemblyID`|`win:UInt64`|이 모듈이 있는 어셈블리의 ID입니다.|
|`ModuleFlags`|`win:UInt32`|0x1: 도메인 중립 모듈.<br /><br /> 0x2: 모듈에 네이티브 이미지 있음.<br /><br /> 0x4: 동적 모듈.<br /><br /> 0x8: 매니페스트 모듈.|
|`Reserved1`|`win:UInt32`|예약된 필드입니다.|
|`ModuleILPath`|`win:UnicodeString`|모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.|
|`ModuleNativePath`|`win:UnicodeString`|있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).|
|`ClrInstanceID`|``win:UInt16``|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|
|`ManagedPdbSignature`|`win:GUID`|이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.|
|`ManagedPdbAge`|`win:UInt32`|이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다. 경우에 따라 파일 이름일 수도 있습니다.|
|`NativePdbSignature`|`win:GUID`|이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).|
|`NativePdbAge`|`win:UInt32`|이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).|
|`NativePdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우). 경우에 따라 파일 이름일 수도 있습니다.|

## <a name="moduledcstart_v2-event"></a>ModuleDCStart_V2 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)

|이벤트|이벤트 ID|Description
|-----------|--------------|-----------------|
|`ModuleDCStart_V2`|153|시작 런다운 중에 모듈을 열거합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|모듈의 고유 ID입니다.|
|`AssemblyID`|`win:UInt64`|이 모듈이 있는 어셈블리의 ID입니다.|
|`ModuleFlags`|`win:UInt32`|0x1: 도메인 중립 모듈.<br /><br /> 0x2: 모듈에 네이티브 이미지 있음.<br /><br /> 0x4: 동적 모듈.<br /><br /> 0x8: 매니페스트 모듈.|
|`Reserved1`|`win:UInt32`|예약된 필드입니다.|
|`ModuleILPath`|`win:UnicodeString`|모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.|
|`ModuleNativePath`|`win:UnicodeString`|있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|
|`ManagedPdbSignature`|`win:GUID`|이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.|
|`ManagedPdbAge`|`win:UInt32`|이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다. 경우에 따라 파일 이름일 수도 있습니다.|
|`NativePdbSignature`|`win:GUID`|이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).|
|`NativePdbAge`|`win:UInt32`|이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).|
|`NativePdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우). 경우에 따라 파일 이름일 수도 있습니다.|

## <a name="moduledcend_v2-event"></a>ModuleDCEnd_V2 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ModuleDCEnd_V2`|154|끝 런다운 중에 모듈을 열거합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`ModuleID`|`win:UInt64`|모듈의 고유 ID입니다.|
|`AssemblyID`|`win:UInt64`|이 모듈이 있는 어셈블리의 ID입니다.|
|`ModuleFlags`|`win:UInt32`|0x1: 도메인 중립 모듈.<br /><br /> 0x2: 모듈에 네이티브 이미지 있음.<br /><br /> 0x4: 동적 모듈.<br /><br /> 0x8: 매니페스트 모듈.|
|`Reserved1`|`win:UInt32`|예약된 필드입니다.|
|`ModuleILPath`|`win:UnicodeString`|모듈에 대 한 CIL (공용 중간 언어) 이미지의 경로 또는 동적 어셈블리인 경우 동적 모듈 이름 (null로 종료 됨)입니다.|
|`ModuleNativePath`|`win:UnicodeString`|있는 경우 모듈 네이티브 이미지의 경로입니다(null로 종료됨).|
|`ClrInstanceID`|`win:UInt16`|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|
|`ManagedPdbSignature`|`win:GUID`|이 모듈과 일치하는 관리되는 PDB(프로그램 데이터베이스)의 GUID 서명입니다.|
|`ManagedPdbAge`|`win:UInt32`|이 모듈과 일치하는 관리되는 PDB에 작성된 기간 수입니다.|
|`ManagedPdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 관리되는 PDB가 빌드된 위치의 경로입니다. 경우에 따라 파일 이름일 수도 있습니다.|
|`NativePdbSignature`|`win:GUID`|이 모듈과 일치하는 네이티브 이미지 생성기(NGen) PDB의 GUID 서명입니다(적용 가능한 경우).|
|`NativePdbAge`|`win:UInt32`|이 모듈과 일치하는 NGen PDB에 작성된 기간 수입니다(적용 가능한 경우).|
|`NativePdbBuildPath`|`win:UnicodeString`|이 모듈과 일치하는 NGen PDB가 빌드된 위치의 경로입니다(적용 가능한 경우). 경우에 따라 파일 이름일 수도 있습니다.|

## <a name="assemblyload_v1-event"></a>AssemblyLoad_V1 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AssemblyLoad_V1`|154|어셈블리가 로드될 때 발생합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|어셈블리의 고유 ID입니다.|
|`AppDomainID`|`win:UInt64`|이 어셈블리의 도메인 ID입니다.|
|`BindingID`|`win:UInt64`|어셈블리 바인딩을 고유하게 식별하는 ID입니다.|
|`AssemblyFlags`|`win:UInt32`|0x1: 도메인 중립 어셈블리.<br /><br /> 0x2: 동적 어셈블리.<br /><br /> 0x4: 어셈블리에 네이티브 이미지 있음.<br /><br /> 0x8: 수집 가능한 어셈블리.|
|`AssemblyName`|`win:UnicodeString`|정규화된 어셈블리 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.

## <a name="assemblyunload_v1-event"></a>AssemblyUnload_V1 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`FireAssemblyUnload_V1`|155|어셈블리가 로드될 때 발생합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|어셈블리의 고유 ID입니다.|
|`AppDomainID`|`win:UInt64`|이 어셈블리의 도메인 ID입니다.|
|`BindingID`|`win:UInt64`|어셈블리 바인딩을 고유하게 식별하는 ID입니다.|
|`AssemblyFlags`|`win:UInt32`|0x1: 도메인 중립 어셈블리.<br /><br /> 0x2: 동적 어셈블리.<br /><br /> 0x4: 어셈블리에 네이티브 이미지 있음.<br /><br /> 0x8: 수집 가능한 어셈블리.|
|`AssemblyName`|`win:UnicodeString`|정규화된 어셈블리 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="assemblydcstart_v1-event"></a>AssemblyDCStart_V1 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`LoaderKeyword` (0x8)|`DomainModuleLoad_V1`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AssemblyDCStart_V1`|155|시작 런다운 중에 어셈블리를 열거합니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyID`|`win:UInt64`|어셈블리의 고유 ID입니다.|
|`AppDomainID`|`win:UInt64`|이 어셈블리의 도메인 ID입니다.|
|`BindingID`|`win:UInt64`|어셈블리 바인딩을 고유하게 식별하는 ID입니다.|
|`AssemblyFlags`|`win:UInt32`|0x1: 도메인 중립 어셈블리.<br /><br /> 0x2: 동적 어셈블리.<br /><br /> 0x4: 어셈블리에 네이티브 이미지 있음.<br /><br /> 0x8: 수집 가능한 어셈블리.|
|`AssemblyName`|`win:UnicodeString`|정규화된 어셈블리 이름입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="assemblyloadstart-event"></a>AssemblyLoadStart 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|`AssemblyLoadStart`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|290|어셈블리 로드가 요청 되었습니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|어셈블리 이름 이름입니다.|
|`AssemblyPath`|`win:UnicodeString`|어셈블리 이름의 경로입니다.|
|`RequestingAssembly`|`win:UnicodeString`|요청 ("부모") 어셈블리의 이름입니다.|
|`AssemblyLoadContext`|`win:UnicodeString`|어셈블리의 로드 컨텍스트입니다.|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|요청 ("부모") 어셈블리의 로드 컨텍스트입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="assemblyloadstop-event"></a>AssemblyLoadStop 이벤트

|이벤트를 발생시키기 위한 키워드|이벤트|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|`AssemblyLoadStart`|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AssemblyLoadStart`|291|어셈블리 로드가 요청 되었습니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|어셈블리 이름 이름입니다.|
|`AssemblyPath`|`win:UnicodeString`|어셈블리 이름의 경로입니다.|
|`RequestingAssembly`|`win:UnicodeString`|요청 ("부모") 어셈블리의 이름입니다.|
|`AssemblyLoadContext`|`win:UnicodeString`|어셈블리의 로드 컨텍스트입니다.|
|`RequestingAssemblyLoadContext`|`win:UnicodeString`|요청 ("부모") 어셈블리의 로드 컨텍스트입니다.|
|`Success`|`win:Boolean`|어셈블리 로드에 성공 했는지 여부를 나타냅니다.|
|`ResultAssemblyName`|`win:UnicodeString`|로드 된 어셈블리의 이름입니다.|
|`ResultAssemblyPath`|`win:UnicodeString`|에서 로드 된 어셈블리의 경로입니다.|
|`Cached`|`win:UnicodeString`|부하가 캐시 되었는지 여부를 나타냅니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="resolutionattempted-event"></a>ResolutionAttempted 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`ResolutionAttempted`|292|어셈블리 로드가 요청 되었습니다.

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|어셈블리 이름 이름입니다.|
|`Stage`|`win:UInt16`|해결 단계입니다.<br/><br/>0: 로드 중을 찾습니다.<br/><br/>1: 어셈블리 로드 컨텍스트</br><br/>2: 응용 프로그램 어셈블리<br/><br/>3: 기본 어셈블리 로드 컨텍스트 대체입니다. <br/><br/>4: 위성 어셈블리를 확인 합니다. <br/><br/>5: 어셈블리 로드 컨텍스트를 확인 합니다.<br/><br/>6: AppDomain 어셈블리를 확인 합니다.
|`AssemblyLoadContext`|`win:UnicodeString`|어셈블리의 로드 컨텍스트입니다.|
|`Result`|`win:UInt16`|확인 시도의 결과입니다.<br/><br/>0: 성공<br/><br/>1: 어셈블리 NotFound<br/><br/>2: 호환 되지 않는 버전<br/><br/>3: 어셈블리 이름이 일치 하지 않습니다.<br/><br/>4: 실패<br/><br/>5: 예외|
|`ResultAssemblyName`|`win:UnicodeString`|확인 된 어셈블리의 이름입니다.|
|`ResultAssemblyPath`|`win:UnicodeString`|에서 확인 된 어셈블리의 경로입니다.|
|`ErrorMessage`|`win:UnicodeString`|예외가 있는 경우 오류 메시지입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="assemblyloadcontextresolvinghandlerinvoked-event"></a>AssemblyLoadContextResolvingHandlerInvoked 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AssemblyLoadContextResolvingHandlerInvoked`|293|[Assemblyloadcontext입니다.](xref:System.Runtime.Loader.AssemblyLoadContext.Resolving) 처리기를 확인 하는 중입니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|어셈블리 이름 이름입니다.|
|`HandlerName`|`win:UnicodeString`|호출 된 처리기의 이름입니다.|
|`AssemblyLoadContext`|`win:UnicodeString`|어셈블리의 로드 컨텍스트입니다.|
|`ResultAssemblyName`|`win:UnicodeString`|확인 된 어셈블리의 이름입니다.|
|`ResultAssemblyPath`|`win:UnicodeString`|에서 확인 된 어셈블리의 경로입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="appdomainassemblyresolvehandlerinvoked-event"></a>AppDomainAssemblyResolveHandlerInvoked 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AppDomainAssemblyResolveHandlerInvoked`|294|<xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>처리기가 호출 되었습니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|어셈블리 이름 이름입니다.|
|`HandlerName`|`win:UnicodeString`|호출 된 처리기의 이름입니다.|
|`ResultAssemblyName`|`win:UnicodeString`|확인 된 어셈블리의 이름입니다.|
|`ResultAssemblyPath`|`win:UnicodeString`|에서 확인 된 어셈블리의 경로입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="assemblyloadfromresolvehandlerinvoked-event"></a>AssemblyLoadFromResolveHandlerInvoked 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`AssemblyLoadFromResolveHandlerInvoked`|295|<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>처리기가 호출 되었습니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`AssemblyName`|`win:UnicodeString`|어셈블리 이름 이름입니다.|
|`IsTrackedLoad`|`win:Boolean`|어셈블리 로드를 추적할지 여부를 지정 합니다.|
|`RequestingAssemblyPath`|`win:UnicodeString`|요청 하는 어셈블리의 경로입니다.|
|`ComputedRequestedAssemblyPath`|`win:UnicodeString`|요청 된 어셈블리의 경로입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|

## <a name="knownpathprobed-event"></a>KnownPathProbed 이벤트

|이벤트를 발생시키기 위한 키워드|수준|
|-----------------------------------|-----------|-----------|
|`Binder` 0x4|정보(4)|

|이벤트|이벤트 ID|Description|
|-----------|--------------|-----------------|
|`KnownPathProbed`|296|어셈블리에 대해 알려진 경로를 검색 했습니다.|

|필드 이름|데이터 형식|Description|
|----------------|---------------|-----------------|
|`FilePath`|`win:UnicodeString`|경로를 검색 했습니다.|
|`Source`|`win:UInt16`|검색 된 경로의 원본입니다.<br/><br/>0x0: 응용 프로그램 어셈블리입니다.<br/><br/>0x1: 응용 프로그램 네이티브 이미지 경로입니다.<br/><br/>0x2: 응용 프로그램 경로입니다.</br><br/>0x3: 플랫폼 리소스 루트.<br/><br/>0x4: 위성 하위 디렉터리입니다.</br>|
|`Result`|`win:UInt32`|프로브에 대 한 HRESULT입니다.|
|`ClrInstanceID`|`win:UInt16`|CoreCLR 인스턴스에 대 한 고유 ID입니다.|
