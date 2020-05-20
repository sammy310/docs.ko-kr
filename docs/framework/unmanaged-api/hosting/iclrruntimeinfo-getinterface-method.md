---
title: ICLRRuntimeInfo::GetInterface 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: c8ac959c192814562488ab916c8462b0baa0d8e6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703652"
---
# <a name="iclrruntimeinfogetinterface-method"></a>ICLRRuntimeInfo::GetInterface 메서드
CLR을 현재 프로세스로 로드 하 고 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)및 [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md)와 같은 런타임 인터페이스 포인터를 반환 합니다.  
  
 이 메서드는 `CorBindTo` [사용 되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md) 섹션의 모든 * 함수를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>매개 변수  
 `rclsid`  
 진행 Coclass의 CLSID 인터페이스입니다.  
  
 `riid`  
 진행 요청 된 인터페이스의 IID입니다 `rclsid` .  
  
 `ppUnk`  
 제한이 쿼리 된 인터페이스에 대 한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`ppUnk`가 null인 경우|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청을 처리할 수 없습니다.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|다른 런타임이 이미 레거시 CLR 버전 2 활성화 정책에 바인딩되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드로 인해 CLR이 로드 되지만 초기화 되지는 않습니다.  
  
 다음 표에서는 및에 대해 지원 되는 조합을 보여 줍니다 `rclsid` `riid` .  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|CLSID_CorMetaDataDispenser|IID_IMetaDataDispenser, IID_IMetaDataDispenserEx|  
|CLSID_CorMetaDataDispenserRuntime|IID_IMetaDataDispenser, IID_IMetaDataDispenserEx|  
|CLSID_CorRuntimeHost|IID_ICorRuntimeHost|  
|CLSID_CLRRuntimeHost|IID_ICLRRuntimeHost|  
|CLSID_TypeNameFactory|IID_ITypeNameFactory|  
|CLSID_CLRDebuggingLegacy|IID_ICorDebug|  
|||  
|CLSID_CLRStrongName|IID_ICLRStrongName|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
