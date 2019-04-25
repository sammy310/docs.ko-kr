---
title: XML 문서(F#)
description: 지원에 대해 알아봅니다 F# 주석에서 문서를 생성 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: c5305dea8832112644710b2863269ef00feddd10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902176"
---
# <a name="xml-documentation"></a>XML 문서

삼중 슬래시 (/ / /)에서 문서를 생성할 수 있습니다 코드 주석에서 F#입니다. XML 주석 코드 파일 (.fs) 또는 서명 (.fsi) 파일의 선언 앞에 있습니다.

## <a name="generating-documentation-from-comments"></a>주석에서 문서 생성

지원 F# 에 대 한 주석에서 문서를 생성 된 것과 다른.NET Framework 언어입니다. 다른.net 언어와 마찬가지로 합니다 [-doc 컴파일러 옵션](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04) 같은 도구를 사용 하 여 설명서로 변환할 수 있는 정보가 포함 된 XML 파일을 만들 수 있습니다 [DocFX](https://dotnet.github.io/docfx/) 또는[ Sandcastle](https://github.com/EWSoftware/SHFB)합니다. 일반적으로 다른.NET Framework 언어로 작성 된 어셈블리를 사용 하 여 용도로 설계 된 도구를 사용 하 여 생성 한 문서 생성의 컴파일된 형태를 기반으로 하는 Api의 뷰를 F# 를 생성 합니다. 특히 도구를 지원 하지 않는 한 F#, 이러한 도구에서 생성 한 문서와 일치 하지 않습니다는 F# API의 보기입니다.

Xml에서 문서를 생성 하는 방법에 대 한 자세한 내용은 참조 하세요. [XML 문서 주석 &#40;C&#35; 프로그래밍 가이드&#41;](https://msdn.microsoft.com/library/b2s063f7)합니다.

## <a name="recommended-tags"></a>권장된 태그

두 가지 방법으로 XML 문서 주석을 기록할 수 있습니다. XML 태그를 사용 하지 않고는 삼중 슬래시 주석에서 직접 설명서 작성 방법은 하나입니다. 이 작업을 수행 하는 경우 전체 주석 텍스트 바로 뒤에 오는 코드 구문에 대 한 요약 설명이으로 간주 됩니다. 각 구문에 대 한 간략 한 요약만 작성 하려는 경우이 메서드를 사용 합니다. 다른 방법은 더 구조화 된 문서를 제공 하는 데 XML 태그를 사용할 것입니다. 두 번째 메서드를 사용 하면 간단히, 추가적인 주의 사항은, 각 매개 변수 및 형식 매개 변수, throw 된 예외에 대 한 설명서 및 반환 값의 설명에 대 한 별도 정보를 지정할 수 있습니다. 다음 표에서 XML 태그에서 인식 되는 F# XML 코드 주석입니다.

|태그 구문|설명|
|----------|-----------|
|**\<c\>**_text_**\</c\>**|형식임 *텍스트* 코드입니다. 이 태그 텍스트를 표시 하는 코드에 대 한 적절 한 글꼴로 설명서 생성기에서 사용할 수 있습니다.|
|**\<summary\>**_text_**\</summary\>**|형식임 *텍스트* 프로그램 요소에 대 한 간략 한 설명입니다. 설명의 하나 또는 두 개의 문장을 일반적으로 됩니다.|
|**\<remarks\>**_text_**\</remarks\>**|형식임 *텍스트* 프로그램 요소에 대 한 보충 정보를 포함 합니다.|
|**\<param name="**_name_**"\>**_description_**\</param\>**|이름 및 함수 또는 메서드 매개 변수에 대 한 설명을 지정합니다.|
|**\<typeparam name="**_name_**"\>**_description_**\</typeparam\>**|이름 및 형식 매개 변수의 설명을 지정합니다.|
|**\<returns\>**_text_**\</returns\>**|형식임 *텍스트* 함수 또는 메서드 반환 값을 설명 합니다.|
|**\<exception cref="**_type_**"\>**_description_**\</exception\>**|생성 될 수 있는 예외 및 throw 되는 상황의 형식을 지정 합니다.|
|**\<see cref="**_reference_**"\>**_text_**\</see\>**|다른 프로그램 요소에 대 한 인라인 링크를 지정합니다. 합니다 *참조* XML 문서 파일에 나타나는 이름입니다. 합니다 *텍스트* 링크에 나타나는 텍스트입니다.|
|**\<seealso cref="**_reference_**"/\>**|다른 형식에 대 한 설명서도 참조 링크를 지정합니다. 합니다 *참조* XML 문서 파일에 나타나는 이름입니다. 설명서 페이지의 맨 아래에 일반적으로 표시 하는 링크를 참조 하세요.|
|**\<para\>**_text_**\</para\>**|텍스트 단락을 지정합니다. 내부 텍스트를 구분 하는 데는이 **주의** 태그입니다.|

## <a name="example"></a>예제

### <a name="description"></a>설명

다음은 서명 파일에는 일반적인 XML 문서 주석입니다.

### <a name="code"></a>코드

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>예제

### <a name="description"></a>설명

다음 예제에서는 XML 태그 없이 대체 메서드를 보여 줍니다. 이 예제에서는 주석에서 전체 텍스트 요약으로 간주 됩니다. 참고는 summary 태그를 명시적으로 지정 하지 않으면 지정할 수 없습니다 다른 태그와 같은 **param** 하거나 **반환** 태그입니다.

### <a name="code"></a>코드

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [컴파일러 옵션](compiler-options.md)
