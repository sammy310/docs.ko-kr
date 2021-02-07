---
description: '자세히 알아보기: ISymUnmanagedMethod 인터페이스'
title: ISymUnmanagedMethod 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 18f87784a959ddc62415592e51d1971ea10f90bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709960"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod 인터페이스

기호 저장소 내의 메서드를 나타냅니다. 이 인터페이스는 형식 관련 특성이 아닌 메서드의 기호 관련 특성에 대 한 액세스를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetNamespace 메서드](isymunmanagedmethod-getnamespace-method.md)|이 메서드가 정의 된 네임 스페이스를 가져옵니다.|  
|[GetOffset 메서드](isymunmanagedmethod-getoffset-method.md)|문서 내의 지정 된 위치에 해당 하는이 메서드 내의 오프셋을 반환 합니다.|  
|[GetParameters 메서드](isymunmanagedmethod-getparameters-method.md)|이 메서드에 대 한 매개 변수를 가져옵니다.|  
|[GetRanges 메서드](isymunmanagedmethod-getranges-method.md)|문서에서 위치가 지정 된 경우이 메서드 내에서 위치가 포함 되는 MSIL (Microsoft 중간 언어)의 범위에 해당 하는 시작 및 종료 오프셋 쌍의 배열을 반환 합니다.|  
|[GetRootScope 메서드](isymunmanagedmethod-getrootscope-method.md)|이 메서드 내에서 루트 어휘 범위를 가져옵니다. 이 범위는 전체 메서드를 포함합니다.|  
|[GetScopeFromOffset 메서드](isymunmanagedmethod-getscopefromoffset-method.md)|이 메서드 내에서 지정 된 오프셋을 둘러싸는 가장 바깥쪽 어휘 범위를 가져옵니다.|  
|[GetSequencePointCount 메서드](isymunmanagedmethod-getsequencepointcount-method.md)|이 메서드 내의 시퀀스 위치 수를 가져옵니다.|  
|[GetSequencePoints 메서드](isymunmanagedmethod-getsequencepoints-method.md)|이 메서드 내의 모든 시퀀스 위치를 가져옵니다.|  
|[GetSourceStartEnd 메서드](isymunmanagedmethod-getsourcestartend-method.md)|이 메서드의 소스에 대 한 시작 및 끝 문서 위치를 가져옵니다.|  
|[GetToken 메서드](isymunmanagedmethod-gettoken-method.md)|이 메서드에 대한 메타데이터 토큰을 반환합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
