---
title: 새 노드를 만들 때 XML 요소 및 특성 이름 확인
ms.date: 03/30/2017
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 0678f7daf5276a905ce890a5f6a0f64993fb08b0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828819"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>새 노드를 만들 때 XML 요소 및 특성 이름 확인
XML DOM(문서 개체 모델)에서는 새 요소 노드나 특성 노드를 만들 때 해당 이름의 유효성을 확인합니다. 이름에 잘못된 문자가 있으면 예외가 throw됩니다. 이름이 유효하고 올바르게 인코딩되었는지 확인하려면 **XmlConvert** 클래스를 사용하여 이름을 인코딩한 다음 애플리케이션 수준에서 다시 디코딩해야 합니다. **XmlWriter** 에는 추가 작업을 수행하여 잘 구성된(Well-Formed) XML이 생성되는지 확인하는 메서드가 있습니다.  
  
## <a name="see-also"></a>참조

- [XML DOM(문서 개체 모델)](xml-document-object-model-dom.md)
