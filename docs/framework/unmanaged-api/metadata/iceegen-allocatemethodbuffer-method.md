---
title: ICeeGen::AllocateMethodBuffer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 8dc7f439cac56c2d55916ff8631ec3095c67680d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008887"
---
# <a name="iceegenallocatemethodbuffer-method"></a>ICeeGen::AllocateMethodBuffer 메서드
메서드에 대해 지정 된 크기의 버퍼를 만들고 메서드의 상대 가상 주소를 가져옵니다.  
  
 이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchBuffer`  
 진행 만들 버퍼의 길이입니다.  
  
 `lpBuffer`  
 제한이 반환 된 버퍼입니다.  
  
 `RVA`  
 제한이 메서드의 상대 가상 주소입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICeeGen 인터페이스](iceegen-interface.md)
