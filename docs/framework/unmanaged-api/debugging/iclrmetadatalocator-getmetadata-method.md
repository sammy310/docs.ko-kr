---
description: '자세히 알아보기: ICLRMetadataLocator:: GetMetadata 메서드'
title: ICLRMetadataLocator::GetMetadata 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: 4a7e8b906b66c4295dd24800d260790526114701
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772618"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata 메서드

이미지의 메타 데이터를 검색 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `imagePath`  
 진행 이미지 파일의 경로를 지정 하는 문자열입니다.  
  
 `imageTimestamp`  
 진행 이미지 파일의 타임 스탬프입니다.  
  
 `imageSize`  
 진행 이미지 파일의 크기입니다.  
  
 `mvid`  
 진행 이미지의 guid (globally unique identifier)입니다.  
  
 `mdRva`  
 진행 메타 데이터의 RVA (상대 가상 주소)입니다. 주소는 이미지 기준 주소를 기준으로 합니다.  
  
 `flags`  
 진행 나중에 사용 하도록 예약 되어 있습니다.  
  
 `bufferSize`  
 진행 메타 데이터를 저장할 버퍼의 크기입니다.  
  
 `buffer`  
 제한이 메타 데이터를 저장할 버퍼입니다.  
  
 `dataSize`  
 제한이 반환 되는 메타 데이터의 크기입니다.  
  
## <a name="remarks"></a>설명  

 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRMetadataLocator 인터페이스](iclrmetadatalocator-interface.md)
