---
title: ISymUnmanagedWriter::Initialize2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Initialize2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Initialize2
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize2 method [.NET Framework debugging]
- Initialize2 method [.NET Framework debugging]
ms.assetid: 93de56b6-4ae8-4cca-acdc-25a434623509
topic_type:
- apiref
ms.openlocfilehash: 041df959139a0be77f40d6aa5655ff15f93fb26f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427952"
---
# <a name="isymunmanagedwriterinitialize2-method"></a>ISymUnmanagedWriter::Initialize2 메서드
이 작성기를 연결할 메타 데이터 내보내기 인터페이스를 설정 하 고 디버깅 기호를 쓸 출력 파일 이름을 설정 합니다. 이 메서드를 사용 하 여 PDB (프로그램 데이터베이스) 파일의 최종 위치를 설정할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Initialize2(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *tempfilename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild,  
    [in] const WCHAR  *finalfilename);  
```  
  
## <a name="parameters"></a>매개 변수  
 `emitter`  
 진행 메타 데이터 내보내기 인터페이스에 대 한 포인터입니다.  
  
 `tempfilename`  
 진행 디버깅 기호가 쓰여진 파일 이름을 포함 하는 `WCHAR`에 대 한 포인터입니다. 파일 이름을 사용하지 않는 작성기에 대해 파일 이름이 지정되면 이 매개 변수는 무시됩니다.  
  
 `pIStream`  
 진행 지정 된 경우 기호 작성기는 `filename` 매개 변수에 지정 된 파일이 아닌 지정 된 <xref:System.Runtime.InteropServices.ComTypes.IStream>으로 기호를 내보냅니다. `pIStream` 매개 변수는 선택적 요소입니다.  
  
 `fFullBuild`  
 [in] 전체 다시 작성 인 경우 `true` 합니다. 증분 컴파일 인 경우 `false` 합니다.  
  
 `finalfilename`  
 진행 PDB 파일의 마지막 위치에 대 한 경로 문자열인 `WCHAR`에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고자료

- [ISymUnmanagedWriter 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [Initialize 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)
