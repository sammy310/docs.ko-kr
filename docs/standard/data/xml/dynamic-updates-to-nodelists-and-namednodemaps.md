---
title: NodeList 및 NamedNodeMap에 대한 동적 업데이트
ms.date: 03/30/2017
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
ms.openlocfilehash: 2e23507000a780246c129d470b525f19b8b3b9c9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827661"
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>NodeList 및 NamedNodeMap에 대한 동적 업데이트
**XmlNodeList** 및 **XmlNamedNodeMap** 에는 노드 집합이 포함되므로, XML 문서를 메모리에 로드하고 수정하려는 경우 W3C(World Wide Web 컨소시엄)에서는 노드 집합을 포함하는 이러한 개체가 동적이어야 한다고 표현합니다. 즉, 원본으로 사용하는 문서가 변경되면 이러한 두 개체의 데이터도 변경되어야 합니다. 따라서 특정 요소의 자식 요소를 모두 포함하는 **XmlNodeList** 인 X 요소가 있다면 X 요소 아래의 문서에 Q 요소를 추가하는 경우 **XmlNodeList** 에도 해당 컬렉션에 새 Q 요소가 추가되어 있어야 합니다. 그 반대의 경우에도 마찬가지입니다. **XmlNodeList** 에 노드가 추가되면 원본으로 사용하는 문서 역시 업데이트됩니다.  
  
## <a name="see-also"></a>참조

- [XML DOM(문서 개체 모델)](xml-document-object-model-dom.md)
