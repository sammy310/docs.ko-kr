---
description: '자세히 알아보기: IMetaDataAssemblyEmit:: SetFileProps 메서드'
title: IMetaDataAssemblyEmit::SetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 482aa11b85eaf05d126c4fcc0d5a1aced85002d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789309"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>IMetaDataAssemblyEmit::SetFileProps 메서드

지정된 `File` 메타데이터 구조를 수정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `file`  
 진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `File` .  
  
 `pbHashValue`  
 진행 파일과 연결 된 해시 데이터에 대 한 포인터입니다.  
  
 `cbHashValue`  
 진행 의 크기 (바이트) `pbHashValue` 입니다.  
  
 `dwFileFlags`  
 진행 파일의 다양 한 특성을 지정 하는 [Corfileflags](corfileflags-enumeration.md) 값의 비트 조합입니다.  
  
## <a name="remarks"></a>설명  

 `File`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineFile](imetadataassemblyemit-definefile-method.md) 메서드를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
