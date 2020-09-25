---
title: '방법: 직렬화 가능한 엔터티 만들기'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: f4528cab21ac678f5d06717d0ce6e7ff7e77d3e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203503"
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
