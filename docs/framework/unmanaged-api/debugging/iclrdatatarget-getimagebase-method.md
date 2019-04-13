---
title: ICLRDataTarget::GetImageBase 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e823911280f52e16c745c9c77fe17b49bd35dc0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129833"
---
# <a name="iclrdatatargetgetimagebase-method"></a>ICLRDataTarget::GetImageBase 메서드
지정된 된 이미지의 기본 메모리 주소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `imagePath`  
 [in] 해당 경로 포함 하는 이미지의 파일 이름입니다.  
  
 `baseAddress`  
 [out] 이미지의 기준 주소를 저장 하는 CLRDATA_ADDRESS 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이미지 파일 이름을 수도 있습니다는 경로 없을 수 있습니다. 경로 지정 하는 경우 일치 하는 이루어집니다 전체 경로입니다. 그렇지 않으면 일치 하는 파일 이름에만 적용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICLRDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
