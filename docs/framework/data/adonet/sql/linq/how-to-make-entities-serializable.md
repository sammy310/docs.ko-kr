---
title: '방법: 직렬화 가능한 엔터티 만들기'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: 5e9d078ed2daacfa48b09693f533e9aade613281
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002704"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="118c5-102">방법: 직렬화 가능한 엔터티 만들기</span><span class="sxs-lookup"><span data-stu-id="118c5-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="118c5-103">코드를 생성할 때 엔터티를 serialize 가능하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118c5-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="118c5-104">엔터티 클래스는 <xref:System.Runtime.Serialization.DataContractAttribute> 특성으로 데코레이팅되고 열은 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성으로 데코레이팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="118c5-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="118c5-105">Visual Studio를 사용 하는 개발자는이를 위해 개체 관계형 디자이너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118c5-105">Developers using Visual Studio can use the Object Relational Designer for this purpose.</span></span>  
  
 <span data-ttu-id="118c5-106">SQLMetal 명령줄 도구를 사용 하는 경우 `unidirectional` 인수를 사용 하 여 **/serialization** 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="118c5-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="118c5-107">자세한 내용은 [SqlMetal.exe(코드 생성 도구)](../../../../tools/sqlmetal-exe-code-generation-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="118c5-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="118c5-108">예제</span><span class="sxs-lookup"><span data-stu-id="118c5-108">Example</span></span>  
 <span data-ttu-id="118c5-109">다음 SQLMetal 명령줄에서는 serialize 가능한 엔터티가 있는 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="118c5-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```console  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```console  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="118c5-110">참조</span><span class="sxs-lookup"><span data-stu-id="118c5-110">See also</span></span>

- [<span data-ttu-id="118c5-111">serialization</span><span class="sxs-lookup"><span data-stu-id="118c5-111">Serialization</span></span>](serialization.md)
- [<span data-ttu-id="118c5-112">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="118c5-112">Creating the Object Model</span></span>](creating-the-object-model.md)
