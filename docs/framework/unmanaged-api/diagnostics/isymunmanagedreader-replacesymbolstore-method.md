---
title: ISymUnmanagedReader::ReplaceSymbolStore 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
ms.openlocfilehash: 3fa94094ad066496cc8a1fc4dd2ccb0ee16b5aac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675843"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a>ISymUnmanagedReader::ReplaceSymbolStore 메서드

기존 기호 저장소를 델타 기호 저장소로 바꿉니다. 이 메서드는 지정 된 델타가 업데이트가 아닌 완전 한 대체 역할을 한다는 점을 제외 하 고 [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) 메서드와 비슷합니다.  
  
> [!NOTE]
> 또는 매개 변수 중 하나만 지정 해야 `filename` `pIStream` 합니다. 을 `filename` 지정 하면 기호 저장소가 해당 파일의 기호를 사용 하 여 업데이트 됩니다. 을 `pIStream` 지정 하면 저장소는의 데이터로 업데이트 됩니다 <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>매개 변수  

 `filename`  
 진행 기호 저장소를 포함 하는 파일의 이름입니다.  
  
 `pIStream`  
 진행 매개 변수의 대 안으로 사용 되는 파일 스트림입니다 `filename` .  
  
## <a name="return-value"></a>반환 값  

 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedReader 인터페이스](isymunmanagedreader-interface.md)
