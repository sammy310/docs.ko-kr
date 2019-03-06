---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 763767514f5f157c676f2e5c86ff9b1e4e64f233
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495249"
---
# <a name="getrawinputdevices"></a>GetRawInputDevices
PresentationHost.exe가 호스트 응용 프로그램과 관련된 원시 입력 장치(휴먼 인터페이스 장치)를 검색할 수 있게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppEnum`  
  
 [out] 에 대 한 포인터를 [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) 원시 입력된 장치를 열거 합니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 HRESULT:  
  
 S_OK- [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) S_OK가 반환 된 경우 PresentationHost.exe에서 사용만 됩니다.  
  
 E_NOTIMPL  
  
## <a name="remarks"></a>설명  
 원시 입력 장치는 키보드, 마우스 및 리모콘과 같은 덜 일반적인 장치를 포함하는 입력 장치 집합입니다.  
  
 원시 입력 장치 목록이 검색된 후 PresentationHost.exe는 WM_INPUT 알림 메시지를 받을 장치를 등록합니다.  
  
## <a name="see-also"></a>참고자료
- [GetRawInputDeviceList](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [FilterInputMessage](filterinputmessage.md)
