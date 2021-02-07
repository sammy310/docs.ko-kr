---
description: '자세히 알아보기: ICorProfilerInfo7 인터페이스'
title: ICorProfilerInfo7 인터페이스
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 7a33472d5562ad57d38291c64f8da7021ae2fe91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737079"
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7 인터페이스

[.NET Framework 4.6.1 이상 버전에서 지원됨]  
  
 새로 정의 된 메타 데이터를 모듈에 적용 하 고 메모리 내 기호 스트림에 대 한 액세스를 제공 하는 메서드를 제공 하는 [ICorProfilerInfo6](icorprofilerinfo6-interface.md) 의 서브 클래스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ApplyMetaData 메서드](icorprofilerinfo7-applymetadata-method.md)|메서드에 의해 새로 정의 된 메타 데이터를 `IMetadataEmit::Define*` 지정 된 모듈에 적용 합니다.|  
|[GetInMemorySymbolsLength 메서드](icorprofilerinfo7-getinmemorysymbolslength-method.md)|메모리 내 기호 스트림의 길이를 반환 합니다.|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|메모리 내 기호 스트림에서 바이트를 읽습니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [프로파일링 인터페이스](profiling-interfaces.md)
