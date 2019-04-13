---
title: ISymUnmanagedBinder 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105821"
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder 인터페이스
비관리 코드의 기호 바인더를 나타냅니다.  
  
> [!IMPORTANT]
>  이 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안 위험이 초래 됩니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetReaderForFile 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|지정 된 메타 데이터 인터페이스 및 파일 이름을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체는 모듈을 사용 하 여 관련 디버깅 기호를 읽습니다.|  
|[GetReaderFromStream 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|지정 된 메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 디버깅 읽을 구조에서 지정 된 기호 저장소 기호입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>참고자료

- [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder2 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [ISymUnmanagedBinder3 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
