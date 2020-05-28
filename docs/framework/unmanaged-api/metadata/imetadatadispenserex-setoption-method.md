---
title: IMetaDataDispenserEx::SetOption 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
ms.openlocfilehash: 0cb0dee7db7faa4c1324d705218934489ec6a4b6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005858"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption 메서드
지정 된 옵션을 현재 메타 데이터 범위의 지정 된 값으로 설정 합니다. 옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `optionId`  
 진행 설정할 옵션을 지정 하는 GUID에 대 한 포인터입니다.  
  
 `pValue`  
 진행 옵션을 설정 하는 데 사용할 값입니다. 이 값의 형식은 지정 된 옵션 형식의 variant 여야 합니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서는 매개 변수가 가리키는 사용 가능한 Guid `optionId` 와 매개 변수에 해당 하는 유효한 값을 보여 줍니다 `pValue` .  
  
|GUID|설명|`pValue`변수에|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|중복 항목을 검사할 항목을 제어 합니다. 새 항목을 만드는 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 메서드를 호출할 때마다 해당 항목이 현재 범위에 이미 있는지 여부를 메서드에 요청할 수 있습니다. 예를 들어 항목이 있는지 확인할 수 있습니다 `mdMethodDef` .이 경우 [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)를 호출 하면 메서드가 현재 범위에 아직 없는지 확인 합니다. 이 검사에서는 지정 된 메서드를 고유 하 게 식별 하는 키 인 부모 유형, 이름 및 시그니처를 사용 합니다.|은 UI4 형식의 variant 여야 하며 [CorCheckDuplicatesFor](corcheckduplicatesfor-enumeration.md) 열거형 값의 조합을 포함 해야 합니다.|  
|MetaDataRefToDefCheck|정의로 변환 되는 참조 된 항목을 제어 합니다. 기본적으로 메타 데이터 엔진은 참조 된 항목이 현재 범위에서 실제로 정의 된 경우 참조 된 항목을 해당 정의로 변환 하 여 코드를 최적화 합니다.|은 UI4 형식의 variant 여야 하며 [Correftodefcheck](correftodefcheck-enumeration.md) 열거형 값의 조합을 포함 해야 합니다.|  
|MetaDataNotificationForTokenMovement|메타 데이터 병합 중에 발생 하는 토큰 다시 매핑에 대 한 제어 콜백을 생성 합니다. [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 메서드를 사용 하 여 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 인터페이스를 설정 합니다.|은 UI4 형식의 variant 여야 하며 [Cornotificationfortokenmovement](cornotificationfortokenmovement-enumeration.md) 열거형 값의 조합을 포함 해야 합니다.|  
|MetaDataSetENC|편집 하며 계속 하기 (ENC)의 동작을 제어 합니다. 한 번에 하나의 동작 모드만 설정할 수 있습니다.|은 UI4 형식의 variant 여야 하며 [Corsetenc](corsetenc-enumeration.md) 열거형의 값을 포함 해야 합니다. 값이 비트 마스크가 아닙니다.|  
|MetaDataErrorIfEmitOutOfOrder|잘못 된 순서로 내보낸 오류를 제어 합니다. 메타 데이터 내보내기 순서가 잘못 되었습니다. 그러나 메타 데이터 엔진에서 선호 하는 순서로 메타 데이터를 내보내는 경우 메타 데이터는 더 간결 하므로 더 효율적으로 검색할 수 있습니다. 메서드를 사용 `IMetaDataEmit::SetHandler` 하 여 [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) 인터페이스를 설정 합니다.|은 UI4 형식의 variant 여야 하며 [CorErrorIfEmitOutOfOrder](corerrorifemitoutoforder-enumeration.md) 열거형 값의 조합을 포함 해야 합니다.|  
|MetaDataImportOption|열거자에서 검색 된 ENC 중에 삭제 된 항목의 종류를 제어 합니다.|은 UI4 형식의 variant 여야 하며 [CorImportOptions 열거형](corimportoptions-enumeration.md) 열거형 값의 조합을 포함 해야 합니다.|  
|Metadatathread Etyoptions|메타 데이터 엔진이 판독기/작성기 잠금을 획득 하 여 스레드 안전을 보장 하는지 여부를 제어 합니다. 기본적으로 엔진은 호출자가 액세스를 단일 스레드로 간주 하므로 잠금을 획득할 수 없습니다. 클라이언트는 메타 데이터 API를 사용할 때 적절 한 스레드 동기화를 유지 관리 하는 일을 담당 합니다.|은 UI4 형식의 variant 여야 하며 [Corthread Etyoptions](corthreadsafetyoptions-enumeration.md) 열거형의 값을 포함 해야 합니다. 값이 비트 마스크가 아닙니다.|  
|MetaDataGenerateTCEAdapters|형식 라이브러리 가져오기에서 COM 연결 지점 컨테이너에 대해 긴밀 하 게 결합 된 이벤트 (TCE) 어댑터를 생성할지 여부를 제어 합니다.|BOOL 형식의 variant 여야 합니다. `pValue`가로 설정 된 경우 `true` 형식 라이브러리 가져오기에서 TCE 어댑터를 생성 합니다.|  
|MetaDataTypeLibImportNamespace|가져오는 형식 라이브러리의 기본이 아닌 네임 스페이스를 지정 합니다.|는 null 값 또는 BSTR 형식의 variant 여야 합니다. `pValue`가 null 값인 경우에는 현재 네임 스페이스가 null로 설정 되 고, 그렇지 않으면 현재 네임 스페이스가 variant의 BSTR 형식에 저장 된 문자열로 설정 됩니다.|  
|MetaDataLinkerOptions|링커가 어셈블리 또는 .NET Framework 모듈 파일을 생성 해야 하는지 여부를 제어 합니다.|은 UI4 형식의 variant 여야 하며 [Corlinkeroptions](corlinkeroptions-enumeration.md) 열거형 값의 조합을 포함 해야 합니다.|  
|MetaDataRuntimeVersion|이 이미지가 빌드된 대상 공용 언어 런타임의 버전을 지정 합니다. 버전은 "v v1.0.3705"와 같은 문자열로 저장 됩니다.|는 null 값, VT_EMPTY 값 또는 BSTR 형식의 variant 여야 합니다. `pValue`가 null 이면 런타임 버전이 null로 설정 됩니다. `pValue`가 VT_EMPTY 경우 버전은 메타 데이터 코드가 실행 되는 mscorwks.dll 버전에서 가져온 기본값으로 설정 됩니다. 그렇지 않으면 런타임 버전이 variant의 BSTR 형식에 저장 된 문자열로 설정 됩니다.|  
|MetaDataMergerOptions|메타 데이터 병합 옵션을 지정 합니다.|는 UI4 형식의 변형 이어야 하며, `MergeFlags` CorHdr .h 파일에 설명 된 열거형 값의 조합을 포함 해야 합니다.|  
|MetaDataPreserveLocalRefs|정의에 대 한 로컬 참조 최적화를 사용 하지 않습니다.|[Corlocalrefpreservation](corlocalrefpreservation-enumeration.md) 열거 된 값의 조합을 포함 해야 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
