---
description: 기타 C# 컴파일러 옵션입니다. 이러한 옵션은 컴파일러에 일반 옵션을 제공합니다.
title: 다른 범주에 맞지 않는 C# 컴파일러 옵션
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- ResponseFiles compiler option [C#]
- NoLogo compiler option [C#]
- NoConfig compiler option [C#]
ms.openlocfilehash: ec7d9c3685c9acb5ca3cda28aca55abb26b836cf
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482445"
---
# <a name="miscellaneous-c-compiler-options"></a>기타 C# 컴파일러 옵션

다음 옵션은 기타 컴파일러 동작을 제어합니다. 새 MSBuild 구문은 **굵게** 표시됩니다. 이전 *csc.exe* 구문은 `code style`에 표시됩니다.

- **ResponseFiles** / `-@`: 추가 옵션에 대한 지시 파일을 읽습니다.
- **NoLogo** / `-nologo`: 컴파일러 저작권 메시지를 표시하지 않습니다.
- **NoConfig** / `-noconfig`: *CSC.RSP* 파일을 자동으로 포함하지 않습니다.

## <a name="responsefiles"></a>ResponseFiles

**ResponseFiles** 옵션을 사용하면 컴파일 옵션과 컴파일할 소스 코드 파일이 포함된 파일을 지정할 수 있습니다.

```xml
<ResponseFiles>response_file</ResponseFiles>
```

`response_file`은 컴파일러 옵션이나 컴파일할 소스 코드 파일이 나열하는 파일을 지정합니다. 컴파일러 옵션 및 소스 코드 파일은 명령줄에 지정된 것처럼 컴파일러에서 처리됩니다. 컴파일에 지시 파일을 둘 이상 지정하려면 여러 지시 파일 옵션을 지정합니다. 지시 파일에서 여러 컴파일러 옵션과 소스 코드 파일이 한 줄에 나타날 수 있습니다. 단일 컴파일러 옵션 사양은 한 줄에 표시되어야 합니다(여러 줄에 걸쳐 있을 수 없음). 지시 파일은 # 기호로 시작하는 주석을 포함할 수 있습니다. 지시 파일 내에서 컴파일러 옵션을 지정하는 것은 명령줄에서 해당 명령을 실행하는 것과 같습니다. 컴파일러는 읽은대로 명령 옵션을 처리합니다. 명령줄 인수는 지시 파일에서 이전에 나열된 옵션을 재정의할 수 있습니다. 반대로 지시 파일의 옵션은 명령줄 또는 다른 지시 파일에서 이전에 나열된 옵션을 재정의합니다. C#에서는 csc.exe 파일과 동일한 디렉터리에 있는 csc.rsp 파일을 제공합니다. 지시 파일 형식에 대한 자세한 내용은 [**NoConfig**](#noconfig)를 참조하세요. Visual Studio 개발 환경에서는 이 컴파일러 옵션을 설정할 수 없으며 프로그래밍 방식으로 변경할 수도 없습니다. 다음은 샘플 지시 파일의 몇 줄입니다.

```console
# build the first output file
-target:exe -out:MyExe.exe source1.cs source2.cs
```

## <a name="nologo"></a>NoLogo

**NoLogo** 옵션은 컴파일러가 시작될 때 로그온 배너의 표시를 억제하고 컴파일하는 동안 정보 메시지를 표시합니다.

```xml
<NoLogo>true</NoLogo>
```

## <a name="noconfig"></a>NoConfig

**NoConfig** 옵션은 *csc.rsp* 파일을 사용하여 컴파일하지 않도록 지시합니다.

```xml
<NoConfig>true</NoConfig>
```

*csc.rsp* 파일은 .NET Framework와 함께 제공되는 모든 어셈블리를 참조합니다. Visual Studio .NET 개발 환경에 포함된 실제 참조는 프로젝트 형식에 따라 달라집니다. *csc.rsp* 파일을 수정하고 모든 컴파일에 포함되어야 하는 추가 컴파일러 옵션을 지정할 수 있습니다. 컴파일러가 *csc.rsp* 파일의 설정을 찾아서 사용하지 않도록 하려면 **NoConfig** 를 지정합니다. 이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.
