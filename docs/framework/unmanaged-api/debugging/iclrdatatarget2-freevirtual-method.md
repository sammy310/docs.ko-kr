---
title: ICLRDataTarget2::FreeVirtual 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
ms.openlocfilehash: 0a36af5b411673081e74aa243ec8e0f8f876f238
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860477"
---
# <a name="iclrdatatarget2freevirtual-method"></a>ICLRDataTarget2::FreeVirtual 메서드
이전에 대상 프로세스의 주소 공간에 할당 된 메모리를 확보 하기 위해 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `addr`  
 진행 해제할 `CLRDATA_ADDRESS` 메모리의 시작 주소를 지정 하는 값입니다.  
  
 `size`  
 진행 해제할 메모리의 크기 (바이트)입니다.  
  
 `typeFlags`  
 진행 메모리 해제를 제어 하는 플래그입니다. Win32 `VirtualFree` 함수를 참조 하세요.  
  
## <a name="remarks"></a>설명  
 메서드 `FreeVirtual` 는 Win32 `VirtualFree` 함수에 대 한 논리 래퍼로 사용 됩니다.  
  
 이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataTarget2 인터페이스](iclrdatatarget2-interface.md)
- [AllocVirtual 메서드](iclrdatatarget2-allocvirtual-method.md)
