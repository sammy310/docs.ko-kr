---
title: IMetaDataEmit::MergeEnd 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
ms.openlocfilehash: 34ecfc2f01f22971e135358806adeea632e02f8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448033"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd 메서드

[IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)에 대 한 하나 이상의 이전 호출로 지정 된 모든 메타 데이터 범위를 현재 범위에 병합 합니다.

## <a name="syntax"></a>구문

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a>매개 변수

이 메서드는 매개 변수를 사용 하지 않습니다.

## <a name="remarks"></a>주의

이 루틴은 `IMetaDataEmit::Merge`에 대 한 이전 호출로 지정 된 모든 가져오기 범위의 메타 데이터에 대 한 실제 병합을 현재 출력 범위로 트리거합니다.

병합에는 다음과 같은 특수 조건이 적용 됩니다.

- 모듈 버전 식별자 (MVID)는 가져오기 범위에서 메타 데이터에 고유 하기 때문에 가져올 수 없습니다.

- 기존 모듈 차원의 속성은 덮어쓰지 않습니다.

  현재 범위에 대해 모듈 속성이 이미 설정 된 경우 모듈 속성을 가져올 수 없습니다. 그러나 현재 범위에서 모듈 속성을 설정 하지 않은 경우에는 처음 발견 될 때 한 번만 가져옵니다. 이러한 모듈 속성이 다시 발생 하면 중복 됩니다. 모든 모듈 속성의 값 (MVID 제외)을 비교 하 고 중복 항목을 찾을 수 없는 경우 오류가 발생 합니다.

- 형식 정의 (`TypeDef`)의 경우 중복 항목이 현재 범위에 병합 되지 않습니다. `TypeDef` 개체는 정규화 된 각 *개체 이름* + *GUID* + *버전 번호*에 대해 중복 항목을 확인 합니다. 이름 또는 GUID에 일치 하는 항목이 있고 다른 두 요소 중 하나가 다르면 오류가 발생 합니다. 그렇지 않고 세 항목이 모두 `MergeEnd` 일치 하는 경우 간단한는 항목이 실제로 중복 되는지 확인 하는 검사를 수행 합니다. 그렇지 않으면 오류가 발생 합니다. 이 간단한 검사는 다음을 찾습니다.

  - 동일한 멤버 선언이 동일한 순서로 발생 합니다. `mdPrivateScope` ( [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형 참조)로 플래그가 지정 된 멤버는이 검사에 포함 되지 않습니다. 특수 하 게 병합 됩니다.

  - 동일한 클래스 레이아웃입니다.

  즉, `TypeDef` 개체가 선언 된 모든 메타 데이터 범위에서 항상 완전히 일관 되 게 정의 되어야 합니다. 클래스에 대 한 멤버 구현이 여러 컴파일 단위에 걸쳐 분산 된 경우 전체 정의는 모든 범위에 표시 되 고 각 범위에는 증분 되지 않는 것으로 간주 됩니다. 예를 들어 매개 변수 이름이 계약과 관련 된 경우 모든 범위에서 동일한 방식으로 내보내야 합니다. 관련이 없는 경우 메타 데이터로 내보내지 않아야 합니다.

  단, `TypeDef` 개체에는 `mdPrivateScope`으로 플래그가 지정 된 증분 멤버가 있을 수 있습니다. 이러한 항목이 발견 되 면 중복을 고려 하지 않고 `MergeEnd`을 현재 범위에 증분 추가 합니다. 컴파일러는 전용 범위를 이해 하므로 컴파일러는 규칙 적용을 담당 해야 합니다.

- Rva (상대 가상 주소)는 가져오거나 병합 되지 않습니다. 컴파일러는이 정보를 다시 내보낼 것으로 예상 됩니다.

- 사용자 지정 특성은 해당 특성이 첨부 된 항목이 병합 될 때만 병합 됩니다. 예를 들어 클래스와 연결 된 사용자 지정 특성은 클래스를 처음 발견할 때 병합 됩니다. 사용자 지정 특성이 컴파일 단위에 해당 하는 `TypeDef` 또는 `MemberDef`와 연결 된 경우 (예: 멤버 컴파일의 타임 스탬프) 병합 되지 않으며 이러한 메타 데이터를 제거 하거나 업데이트 하는 것이 컴파일러에 해당 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** Cor

**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.

**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>참고 항목

- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
