---
title: 워크플로 솔루션에 서비스 참조 추가
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 7197ae991207efd60ea398794c7c23f427f6b0cc
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964209"
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a>워크플로 솔루션에 서비스 참조 추가

워크플로 애플리케이션에서 서비스 참조를 추가하는 작업은 일반적인 WCF 애플리케이션과 약간 다르게 작동합니다. **> 서비스 참조 추가** 를 선택 하 고 서비스에 대 한 URL을 지정 하면 메타 데이터가 다운로드 되 고에 대 한 참조를 추가한 wcf 서비스 또는 wcf 워크플로 서비스를 호출할 수 있는 사용자 지정 작업이 생성 됩니다. 서비스 참조를 추가한 후 생성된 활동이 빌드되도록 솔루션을 다시 빌드합니다. 솔루션을 다시 빌드한 후 생성된 활동이 워크플로 디자이너 도구 상자에 나타납니다. 그러나 워크플로 솔루션 내에서 서비스 참조를 추가하는 경우에만 이러한 과정이 진행됩니다. 다음 웹 캐스트는 다른 형식의 프로젝트에서 서비스 참조를 추가 하는 방법을 보여 줍니다. [웹 프로젝트의 워크플로에서 WCF 서비스를 호출](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)합니다.

동일한 작업 이름이 포함된 서비스에 대한 서비스 참조를 둘 이상 추가하면 문제가 발생합니다. 생성된 활동이 첫 번째 서비스 작업만 호출합니다. 이 문제를 해결하려면 해당 서비스 작업을 구분하도록 서비스 작업의 이름을 변경하거나 생성된 각 활동에서 엔드포인트 구성 이름을 변경합니다.

## <a name="see-also"></a>참조

- [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [웹 프로젝트의 워크플로에서 WCF 서비스 호출](https://docs.microsoft.com/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
