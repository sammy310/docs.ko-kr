---
title: ISymUnmanagedReader::UpdateSymbolStore 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.UpdateSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::UpdateSymbolStore
helpviewer_keywords:
- UpdateSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::UpdateSymbolStore method [.NET Framework debugging]
ms.assetid: 4a17d723-86b9-4f27-bd0d-b70c3259011c
topic_type:
- apiref
ms.openlocfilehash: 6670d985eed4c55550b23d3f4110ee20f3b75661
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675830"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore 메서드

기존 기호 저장소를 델타 기호 저장소로 업데이트합니다. 이 메서드는 편집 하며 계속 하기 시나리오에서 델타를 원래 PE (이식 가능한 실행) 파일에 일치 하도록 기호 저장소를 업데이트 하는 데 사용 됩니다.  
  
> [!NOTE]
> 또는 매개 변수 중 하나만 지정 해야 `filename` `pIStream` 합니다. 을 `filename` 지정 하면 기호 저장소가 해당 파일의 기호를 사용 하 여 업데이트 됩니다. 을 `pIStream` 지정 하면 저장소는의 데이터로 업데이트 됩니다 <xref:System.Runtime.InteropServices.ComTypes.IStream> .  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT UpdateSymbolStore (  
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
