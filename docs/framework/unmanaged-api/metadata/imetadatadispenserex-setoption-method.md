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
ms.openlocfilehash: f8e85a670d04e5825653864484b7ccd9ce747949
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175904"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption 메서드
지정된 옵션을 현재 메타데이터 범위에 대해 지정된 값으로 설정합니다. 이 옵션은 현재 메타데이터 범위에 대한 호출을 처리하는 방법을 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `optionId`  
 【인】 설정할 옵션을 지정하는 GUID에 대한 포인터입니다.  
  
 `pValue`  
 【인】 옵션을 설정하는 데 사용할 값입니다. 이 값의 형식은 지정된 옵션 형식의 변형이어야 합니다.  
  
## <a name="remarks"></a>설명  
 다음 표에는 `optionId` 매개 변수가 가리킬 수 있는 사용 가능한 GUID와 매개 변수에 대한 해당 유효한 값이 나열되어 `pValue` 있습니다.  
  
|GUID|Description|`pValue`매개 변수|  
|----------|-----------------|------------------------|  
|메타데이터체크중복|중복 항목을 검사하는 항목을 제어합니다. 새 항목을 만드는 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 메서드를 호출할 때마다 해당 메서드에 현재 범위에 항목이 이미 있는지 여부를 확인하도록 요청할 수 있습니다. 예를 들어 항목의 `mdMethodDef` 존재를 확인할 수 있습니다. 이 경우 [IMetaDataEmit::DefineMethod을](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)호출하면 메서드가 현재 범위에 아직 없는지 확인합니다. 이 검사에서는 지정된 메서드(부모 유형, 이름 및 서명)를 고유하게 식별하는 키를 사용합니다.|UI4 형식의 변형이어야 하며 [CorCheckDuplicates열거지의](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) 값의 조합을 포함해야 합니다.|  
|메타데이터레프토데프체크|참조된 항목을 정의로 변환하는 컨트롤입니다. 기본적으로 메타데이터 엔진은 참조된 항목이 현재 범위에 실제로 정의된 경우 참조된 항목을 정의로 변환하여 코드를 최적화합니다.|형식 UI4의 변형이어야 하며 [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) 열거형값의 조합을 포함해야 합니다.|  
|메타 데이터 알림토큰 이동|메타데이터 병합 중에 발생하는 토큰 다시 맵을 제어하여 콜백을 생성합니다. [IMetaDataEmit::SetHandler 메서드를](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 사용하여 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 인터페이스를 설정합니다.|형식 UI4의 변형이어야 하며 [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) 열거형의 값의 조합을 포함해야 합니다.|  
|메타데이터세텐|ENC(편집 및 계속)의 동작을 제어합니다. 한 번에 하나의 동작 모드만 설정할 수 있습니다.|형식 UI4의 변형이어야 하며 [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) 열거형값을 포함해야 합니다. 값은 비트 마스크가 아닙니다.|  
|메타데이터오류이엠티아웃오브오더|순서가 바도 없는 오류를 내보낸 컨트롤은 콜백을 생성합니다. 메타데이터를 순서대로 내보내는 것은 치명적이지 않습니다. 그러나 메타데이터 엔진에서 선호하는 순서로 메타데이터를 내림차순으로 내림하면 메타데이터가 더 작아서 보다 효율적으로 검색할 수 있습니다. 이 `IMetaDataEmit::SetHandler` 방법을 사용하여 [IMetaDataError 인터페이스를](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) 설정합니다.|형식 UI4의 변형이어야 하며 [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) 열거형의 값의 조합을 포함해야 합니다.|  
|메타데이터가져오기 옵션|ENC 중에 삭제된 항목의 종류를 열거형에서 검색하는 컨트롤입니다.|형식 UI4의 변형이어야 하며 [CorImportOptions 열거형](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) 의 값의 조합을 포함해야 합니다.|  
|메타데이터스레드안전옵션|메타데이터 엔진이 판독기/기록기 잠금을 가져오는지 여부를 제어하여 스레드 안전을 보장합니다. 기본적으로 엔진은 액세스가 호출자에서 단일 스레드로 가정하므로 잠금이 없습니다. 클라이언트는 메타데이터 API를 사용할 때 적절한 스레드 동기화를 유지 관리해야 합니다.|형식 UI4의 변형이어야 하며 [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) 열거형의 값을 포함해야 합니다. 값은 비트 마스크가 아닙니다.|  
|메타데이터생성TCE어댑터|형식 라이브러리 가져오기가 COM 연결 지점 컨테이너에 대해 밀접하게 결합된 이벤트(TCE) 어댑터를 생성할지 여부를 제어합니다.|BOOL 형식의 변형이어야 합니다. 로 설정된 경우 `pValue` 형식 라이브러리 가져오기는 TCE 어댑터를 생성합니다. `true`|  
|메타데이터타이프리브인더네임스페이스|가져오는 형식 라이브러리에 대해 기본이 아닌 네임스페이스를 지정합니다.|null 값 또는 BSTR 형식의 변형이어야 합니다. null `pValue` 값인 경우 현재 네임스페이스는 null로 설정됩니다. 그렇지 않으면 현재 네임스페이스가 변형의 BSTR 형식에 있는 문자열로 설정됩니다.|  
|메타데이터링커옵션|링커가 어셈블리또는 .NET Framework 모듈 파일을 생성할지 여부를 제어합니다.|UI4 형식의 변형이어야 하며 [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) 열거형의 값의 조합을 포함해야 합니다.|  
|메타데이터런타임버전|이 이미지가 빌드된 공통 언어 런타임 버전을 지정합니다. 버전은 "v1.0.3705"와 같은 문자열로 저장됩니다.|null 값, VT_EMPTY 값 또는 BSTR 형식의 변형이어야 합니다. null인 경우 `pValue` 런타임 버전이 null로 설정됩니다. VT_EMPTY `pValue` 경우 버전은 메타데이터 코드가 실행되는 Mscorwks.dll 버전에서 가져온 기본값으로 설정됩니다. 그렇지 않으면 런타임 버전이 변형의 BSTR 형식에 있는 문자열로 설정됩니다.|  
|메타데이터머어옵션|메타데이터 병합 옵션을 지정합니다.|UI4 형식의 변형이어야 하며 CorHdr.h 파일에 설명된 `MergeFlags` 열거형 값의 조합을 포함해야 합니다.|  
|메타데이터보존로컬참조|로컬 참조를 정의로 최적화하지 않도록 설정합니다.|[CorLocalRef보존](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) 열거형의 값의 조합을 포함해야 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
