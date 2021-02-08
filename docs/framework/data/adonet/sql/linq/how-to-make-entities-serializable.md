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
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="8ced2-103">방법: 직렬화 가능한 엔터티 만들기</span><span class="sxs-lookup"><span data-stu-id="8ced2-103">How to: Make Entities Serializable</span></span>

<span data-ttu-id="8ced2-104">코드를 생성할 때 엔터티를 serialize 가능하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ced2-104">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="8ced2-105">엔터티 클래스는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성으로 데코레이팅되고 열은 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성으로 데코레이팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ced2-105">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="8ced2-106">Visual Studio를 사용 하는 개발자는이를 위해 개체 관계형 디자이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ced2-106">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="8ced2-107">SQLMetal 명령줄 도구를 사용 하는 경우에는 인수와 함께 **/cks** 옵션을 사용 `unidirectional` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ced2-107">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="8ced2-108">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ced2-108">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ced2-109">예제</span><span class="sxs-lookup"><span data-stu-id="8ced2-109">Example</span></span>  

 <span data-ttu-id="8ced2-110">다음 SQLMetal 명령줄에서는 serialize 가능한 엔터티가 있는 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8ced2-110">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ced2-111">참조</span><span class="sxs-lookup"><span data-stu-id="8ced2-111">See also</span></span>

- [<span data-ttu-id="8ced2-112">serialization</span><span class="sxs-lookup"><span data-stu-id="8ced2-112">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="8ced2-113">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="8ced2-113">Creating the Object Model</span></span>](creating-the-object-model.md)
