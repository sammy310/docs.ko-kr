---
title: COR_PRF_MODULE_FLAGS 열거형
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
ms.openlocfilehash: 12e7faa8d9fee7698de9d9734f522d818f225c84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500821"
---
# <a name="cor_prf_module_flags-enumeration"></a>COR_PRF_MODULE_FLAGS 열거형
모듈의 속성을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|모듈이 디스크에서 로드 되었습니다.|  
|COR_PRF_MODULE_NGEN|네이티브 이미지 생성기 (Ngen.exe)에서 모듈을 생성 했습니다.|  
|COR_PRF_MODULE_DYNAMIC|모듈은 네임 스페이스의 메서드에 의해 만들어졌습니다 <xref:System.Reflection.Emit?displayProperty=nameWithType> .|  
|COR_PRF_MODULE_COLLECTIBLE|모듈의 수명은 가비지 수집기에 의해 관리 됩니다.|  
|COR_PRF_MODULE_RESOURCE|모듈은 메타 데이터를 포함 하지 않으며 리소스로 엄격히 사용 됩니다. 이 비트의 관리 되는 값은 <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> 메서드입니다.|  
|COR_PRF_MODULE_FLAT_LAYOUT|메모리에서 모듈의 레이아웃은 매핑되지 않고 플랫입니다. 모듈에이 비트가 설정 되어 있으면 PE (이식 가능한 실행) 파일 헤더에서 직접 정보를 읽는 프로파일러에서 헤더의 Rva (상대 가상 주소)를 해석할 때 주의 해야 합니다.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Windows 런타임 콘텐츠 형식 플래그는이 모듈의 어셈블리에 대 한 메타 데이터에 설정 됩니다. 이는 모든 Windows 메타 데이터 (winmd) 모듈의 경우입니다.|  
  
## <a name="remarks"></a>설명  
 COR_PRF_MODULE_FLAGS의 비트는 `pdwModuleFlags` [ICorProfilerInfo3:: GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) 메서드의 output 매개 변수에서 프로파일러로 반환 됩니다. 둘 이상의 플래그를 조합 하 여 사용할 수 있지만 모든 조합을 사용할 수 있는 것은 아닙니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 열거형](profiling-enumerations.md)
