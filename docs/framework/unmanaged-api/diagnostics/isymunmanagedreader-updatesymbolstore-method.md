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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f62c954bf9d73ab564eba388e742794a330362d4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080503"
---
# <a name="isymunmanagedreaderupdatesymbolstore-method"></a>ISymUnmanagedReader::UpdateSymbolStore 메서드
기존 기호 저장소를 델타 기호 저장소로 업데이트합니다. 이 메서드는 원래 이식 가능한 실행 파일 (PE) 파일에 대 한 델타에 맞게 기호 저장소를 업데이트 하려면 편집 하며 계속 하기 시나리오에서 사용 됩니다.  
  
> [!NOTE]
>  중 하나만 지정 해야 합니다 `filename` 또는 `pIStream` 매개 변수를 둘 다. 경우 `filename` 를 지정 하면 해당 파일에서 기호를 사용 하 여 기호 저장소 업데이트 됩니다. 하는 경우 `pIStream` 를 지정 하면 저장소의 데이터로 업데이트 됩니다는 <xref:System.Runtime.InteropServices.ComTypes.IStream>합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT UpdateSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a>매개 변수  
 `filename`  
 [in] 기호 저장소를 포함 하는 파일의 이름입니다.  
  
 `pIStream`  
 [in] 대 안으로 사용 되는 파일 스트림을 `filename` 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
