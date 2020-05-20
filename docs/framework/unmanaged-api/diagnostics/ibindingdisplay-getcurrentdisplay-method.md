---
title: IBindingDisplay::GetCurrentDisplay 메서드
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
ms.openlocfilehash: 6fe8c3266a8c9a52cd1022589cd68485c4326fd1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442191"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a>IBindingDisplay::GetCurrentDisplay 메서드
현재 바인딩 표시 정보를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `display`  
 [out, retval] 바인딩 표시 정보를 포함 하는 safearray에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 [IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) 메서드는 이전에 성공 했 고 프로그램은 디버거에서 중지 되어야 합니다.  
  
 호출자는 `SAFEARRAY` [Safearraydestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)를 사용 하 여 반환 된 메모리의 할당을 취소 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** BindingDisplay. h  
  
 **라이브러리:** BindingDisplay .idl  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IBindingDisplay 인터페이스](ibindingdisplay-interface.md)
- [InitializeForProcess 메서드](ibindingdisplay-initializeforprocess-method.md)
