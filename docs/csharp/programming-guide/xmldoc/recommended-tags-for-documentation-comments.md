---
title: 문서 주석에 대한 권장 태그 - C# 프로그래밍 가이드
description: 문서 주석용 권장 태그에 대해 알아봅니다. 권장 태그 목록 및 사용 가능한 추가 리소스를 확인합니다.
ms.date: 01/21/2020
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 65bca6f979c5ffd91507b571a4f049377315192d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381517"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>문서 주석에 대한 권장 태그(C# 프로그래밍 가이드)

C# 컴파일러는 코드의 문서 주석을 처리하고 **/doc** 명령줄 옵션에서 지정한 이름의 파일에 XML로 형식을 지정합니다. 컴파일러에서 생성한 파일을 기반으로 해서 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [DocFX](https://dotnet.github.io/docfx/) 또는 [Sandcastle](https://github.com/EWSoftware/SHFB)과 같은 도구를 사용하면 됩니다.

태그는 형식, 형식 멤버 등의 코드 구문에서 처리됩니다.

> [!NOTE]
> 네임스페이스에는 문서 주석을 적용할 수 없습니다.  
  
 컴파일러는 유효한 XML인 태그를 모두 처리합니다. 다음 태그는 사용자 문서에서 일반적으로 사용되는 기능을 제공합니다.  
  
## <a name="tags"></a>Tags  
  
|||||  
|---|---|---|---|
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|[\<value>](./value.md)  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<inheritdoc>](./inheritdoc.md)|[\<returns>](./returns.md)|
  
(\* 컴파일러에서 구문을 확인함을 나타냅니다.)

문서 주석의 텍스트에 꺾쇠 괄호를 표시하려면 각각 `&lt;` 및 `&gt;`인 `<` 및 `>`의 HTML 인코딩을 사용합니다. 이 인코딩은 다음 예제에서 확인할 수 있습니다.

```csharp
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [-doc(C# 컴파일러 옵션)](../../language-reference/compiler-options/doc-compiler-option.md)
- [XML 문서 주석](./index.md)
