---
title: XML 문서
description: '주석에서 문서를 생성 하기 위한 F #의 지원에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 03d14cef910d149f0c7a2f3a49c8cf4606ac5305
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556579"
---
# <a name="xml-documentation"></a>XML 문서

F #에서 삼중 슬래시 (///) 코드 주석으로 문서를 생성할 수 있습니다. XML 주석은 코드 파일 (fs) 또는 서명 (. fsi.exe) 파일의 선언 앞에 올 수 있습니다.

## <a name="generating-documentation-from-comments"></a>주석에서 설명서 생성

주석에서 문서를 생성 하기 위한 F #의 지원은 다른 .NET Framework 언어의 경우와 동일 합니다. 다른 .NET Framework 언어와 마찬가지로 [-doc 컴파일러 옵션](./compiler-options.md) 을 사용 하면 [Docfx](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)와 같은 도구를 사용 하 여 문서로 변환할 수 있는 정보를 포함 하는 XML 파일을 생성할 수 있습니다. 다른 .NET Framework 언어로 작성 된 어셈블리에서 사용 하도록 디자인 된 도구를 사용 하 여 생성 된 설명서는 일반적으로 컴파일된 형식의 F # 구문을 기반으로 하는 Api 뷰를 생성 합니다. Tools에서 F #을 구체적으로 지원 하지 않는 한 이러한 도구에서 생성 된 설명서는 API의 F # 뷰와 일치 하지 않습니다.

XML에서 문서를 생성 하는 방법에 대 한 자세한 내용은 [Xml 문서 주석 &#40;C&#35; 프로그래밍 가이드&#41;](../../csharp/programming-guide/xmldoc/index.md)를 참조 하세요.

## <a name="recommended-tags"></a>권장 태그

XML 문서 주석을 작성 하는 방법에는 두 가지가 있습니다. 한 가지 방법은 XML 태그를 사용 하지 않고 삼중 슬래시 주석에서 직접 설명서를 작성 하는 것입니다. 이렇게 하면 전체 주석 텍스트가 바로 다음에 오는 코드 구문에 대 한 요약 설명서로 사용 됩니다. 각 구문에 대 한 간략 한 요약만 작성 하려는 경우이 메서드를 사용 합니다. 다른 방법은 XML 태그를 사용 하 여 더 구조적인 설명서를 제공 하는 것입니다. 두 번째 방법을 사용 하면 짧은 요약, 추가 설명, 각 매개 변수 및 형식 매개 변수와 throw 된 예외에 대 한 설명서 및 반환 값에 대 한 설명과 같은 별도의 메모를 지정할 수 있습니다. 다음 표에서는 F # XML 코드 주석에서 인식 되는 XML 태그에 대해 설명 합니다.

|태그 구문|Description|
|----------|-----------|
|**\<c\>**_본문_**\</c\>**|*텍스트* 를 코드로 지정 합니다. 문서 생성기는이 태그를 사용 하 여 코드에 적절 한 글꼴로 텍스트를 표시할 수 있습니다.|
|**\<summary\>**_본문_**\</summary\>**|*텍스트* 를 프로그램 요소에 대 한 간단한 설명으로 지정 합니다. 설명은 일반적으로 하나 또는 두 개의 문장입니다.|
|**\<remarks\>**_본문_**\</remarks\>**|*텍스트* 에 프로그램 요소에 대 한 보충 정보가 포함 되도록 지정 합니다.|
|**\<param name="**_name_**"\>**_한_**\</param\>**|함수 또는 메서드 매개 변수의 이름 및 설명을 지정 합니다.|
|**\<typeparam name="**_name_**"\>**_한_**\</typeparam\>**|형식 매개 변수에 대 한 이름 및 설명을 지정 합니다.|
|**\<returns\>**_본문_**\</returns\>**|함수 또는 메서드의 반환 값을 설명 하는 *텍스트* 를 지정 합니다.|
|**\<exception cref="**_type_**"\>**_한_**\</exception\>**|생성할 수 있는 예외의 형식 및 예외가 throw 되는 상황을 지정 합니다.|
|**\<see cref="**_reference_**"\>**_본문_**\</see\>**|다른 프로그램 요소에 대 한 인라인 링크를 지정 합니다. *참조* 는 XML 문서 파일에 표시 되는 이름입니다. *텍스트* 는 링크에 표시 되는 텍스트입니다.|
|**\<seealso cref="**_reference_**"/\>**|다른 형식에 대 한 설명서 링크도 참조 합니다. *참조* 는 XML 문서 파일에 표시 되는 이름입니다. 링크도 일반적으로 설명서 페이지의 아래쪽에 표시 됩니다.|
|**\<para\>**_본문_**\</para\>**|텍스트 단락을 지정 합니다. 이는 **설명** 태그 내에서 텍스트를 구분 하는 데 사용 됩니다.|

## <a name="example"></a>예제

### <a name="description"></a>Description

다음은 서명 파일의 일반적인 XML 문서 주석입니다.

### <a name="code"></a>코드

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>예제

### <a name="description"></a>Description

다음 예제에서는 XML 태그가 없는 대체 메서드를 보여 줍니다. 이 예제에서는 주석의 전체 텍스트를 요약으로 간주 합니다. 요약 태그를 명시적으로 지정 하지 않은 경우에는 **매개 변수** 또는 태그를 **반환** 하는 등의 다른 태그를 지정 하면 안 됩니다.

### <a name="code"></a>코드

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>참조

- [F# 언어 참조](index.md)
- [컴파일러 옵션](compiler-options.md)
