---
title: GetWin32ResBlob 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684514"
---
# <a name="getwin32resblob-method"></a>GetWin32ResBlob 메서드

Win32 리소스 blob을 검색 합니다. 어셈블리 옵션을 설정한 후이 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>매개 변수  

 `AssemblyID`  
 어셈블리의 ID입니다.  
  
 `FileToken`  
 Win32 버전 리소스를 생성할 때 사용할 파일 이름을 검색 하는 데 사용 되는 파일 토큰입니다.  
  
 `fDll`  
 파일이 DLL 이면 TRUE이 고, EXE의 경우 false입니다.  
  
 `pszIconFile`  
 리소스 blob에 삽입할 선택적 아이콘입니다.  
  
 `ppResBlob`  
 리소스 blob을 받습니다.  
  
 `pcbResBlob`  
 Blob의 크기를 수신 합니다.  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면 S_OK을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 Alink 필요  
  
## <a name="see-also"></a>참조

- [IALink 인터페이스](ialink-interface.md)
- [IALink2 인터페이스](ialink2-interface.md)
- [ALink API](index.md)
