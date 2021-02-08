---
description: '방법에 대 한 자세한 정보: 방법: 엔터티를 직렬화 가능 하도록 만들기'
title: '방법: 직렬화 가능한 엔터티 만들기'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: cb2253d7933f3584543b4b030bc8b5aa3cc62921
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785941"
---
# <a name="how-to-make-entities-serializable"></a>방법: 직렬화 가능한 엔터티 만들기

코드를 생성할 때 엔터티를 serialize 가능하게 만들 수 있습니다. 엔터티 클래스는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성으로 데코레이팅되고 열은 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성으로 데코레이팅됩니다.  
  
 Visual Studio를 사용 하는 개발자는이를 위해 개체 관계형 디자이너를 사용할 수 있습니다.  
  
 SQLMetal 명령줄 도구를 사용 하는 경우에는 인수와 함께 **/cks** 옵션을 사용 `unidirectional` 합니다. 자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.  
  
## <a name="example"></a>예제  

 다음 SQLMetal 명령줄에서는 serialize 가능한 엔터티가 있는 파일을 생성합니다.  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a>참조

- [serialization](serialization.md)
- [개체 모델 만들기](creating-the-object-model.md)
