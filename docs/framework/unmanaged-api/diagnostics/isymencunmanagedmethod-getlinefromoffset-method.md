---
title: ISymENCUnmanagedMethod::GetLineFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetLineFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetLineFromOffset
helpviewer_keywords:
- GetLineFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetLineFromOffset method [.NET Framework debugging]
ms.assetid: cc09bad2-fb34-4d13-a521-6ec7b1a1d915
topic_type:
- apiref
ms.openlocfilehash: d9a7b18e90a3038c1ffb634ccc7315143875c809
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441918"
---
# <a name="isymencunmanagedmethodgetlinefromoffset-method"></a>ISymENCUnmanagedMethod::GetLineFromOffset 메서드
오프셋과 연결 된 줄 정보를 가져옵니다. Offset 매개 변수 ( `dwOffset` )가 시퀀스 위치가 아닌 경우이 메서드는 이전 오프셋과 관련 된 줄 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLineFromOffset(  
     [in]  ULONG32   dwOffset,  
     [out] ULONG32*  pline,  
     [out] ULONG32*  pcolumn,  
     [out] ULONG32*  pendLine,  
     [out] ULONG32*  pendColumn,  
     [out] ULONG32*  pdwStartOffset);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwOffset`  
 진행 `ULONG32`오프셋을 포함 하는입니다.  
  
 `pline`  
 제한이 줄을 수신 하는에 대 한 포인터 `ULONG32` 입니다.  
  
 `pcolumn`  
 제한이 열을 수신 하는에 대 한 포인터 `ULONG32` 입니다.  
  
 `pendLine`  
 제한이 `ULONG32`끝 줄을 수신 하는에 대 한 포인터입니다.  
  
 `pendColumn`  
 제한이 `ULONG32`끝 열을 수신 하는에 대 한 포인터입니다.  
  
 `pdwStartOffset`  
 제한이 연결 된 시퀀스 위치를 수신 하는에 대 한 포인터입니다 `ULONG32` .  
  
## <a name="return-value"></a>Return Value  
 메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymENCUnmanagedMethod 인터페이스](isymencunmanagedmethod-interface.md)
