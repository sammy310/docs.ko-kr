---
title: CorpubPublish Coclass
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: 24d245bbb0f9ac86e321491e0af3b66b1e011baa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789214"
---
# <a name="corpubpublish-coclass"></a>CorpubPublish Coclass
애플리케이션 도메인 및 프로세스에 대한 정보를 게시하기 위한 인터페이스를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|[ICorPublish 인터페이스](icorpublish-interface.md)|프로세스 및 해당 프로세스의 응용 프로그램 도메인에 대 한 정보를 게시 하는 메서드를 제공 합니다.|  
|[ICorPublishAppDomain 인터페이스](icorpublishappdomain-interface.md)|프로세스의 응용 프로그램 도메인에 대 한 정보를 나타내고 제공 합니다.|  
|[ICorPublishAppDomainEnum 인터페이스](icorpublishappdomainenum-interface.md)|프로세스 내에 현재 존재 하는 응용 프로그램 도메인의 컬렉션을 트래버스하는 메서드를 제공 합니다.|  
|[ICorPublishProcess 인터페이스](icorpublishprocess-interface.md)|컴퓨터에서 실행 중인 프로세스를 나타냅니다.|  
|[ICorPublishProcessEnum 인터페이스](icorpublishprocessenum-interface.md)|컴퓨터에서 실행 중인 프로세스의 컬렉션을 트래버스하는 메서드를 제공 합니다.|  
  
## <a name="remarks"></a>주의  
 일반적인 게시 시나리오에는 응용 프로그램 도메인 내 컴퓨터에서 실행 되는 관리 코드를 디버깅 하려는 개발자가 포함 됩니다. 호스팅 환경이 프로세스 내에서 둘 이상의 응용 프로그램 도메인을 실행할 수 있습니다. 개발자는 그래픽 사용자 인터페이스를 사용 하거나 다른 방법을 사용 하 여 컴퓨터에서 실행 중인 모든 프로세스를 나열 하 고 특정 프로세스를 선택 하려고 합니다. 이 목록에는 관리 코드를 실행 하는 프로세스 내의 모든 응용 프로그램 도메인이 포함 되어야 합니다. 그러면 개발자는 특정 응용 프로그램 도메인을 식별 하 고 해당 도메인에 디버거를 연결할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub. idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅](index.md)
