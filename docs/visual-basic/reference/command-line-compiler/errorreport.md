---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6a1c8fce17e3e5a54366c2ff4dff4e6aa668f56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408662"
---
# <a name="-errorreport"></a>-errorreport

Visual Basic 컴파일러에서 내부 컴파일러 오류를 보고하는 방식을 지정합니다.

## <a name="syntax"></a>구문

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a>설명

이 옵션은 Microsoft Visual Basic 팀에 Visual Basic ICE(내부 컴파일러 오류)를 보고하는 편리한 방법을 제공합니다. 기본적으로 컴파일러는 Microsoft에 정보를 보내지 않습니다. 그러나 내부 컴파일러 오류가 발생하는 경우 이 옵션을 사용하면 Microsoft에 오류를 보고할 수 있습니다. 이 정보는 Microsoft 엔지니어가 원인을 파악하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선하는 데 도움이 될 수 있습니다.

사용자가 보고서를 보내는 능력은 컴퓨터 및 사용자 정책 권한에 따라 달라집니다.

다음 표에는 `-errorreport` 옵션의 영향이 요약되어 있습니다.

|옵션|동작|
|---|---|
|`prompt`|내부 컴파일러 오류가 발생하는 경우 컴파일러에서 수집한 정확한 데이터를 볼 수 있도록 대화 상자가 나타납니다. 오류 보고서에 중요한 정보가 있는지 확인하고 Microsoft로 전송할지 여부를 결정할 수 있습니다. 보고서를 전송하기로 결정하고 컴퓨터 및 사용자 정책 설정에서 허용하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.|
|`queue`|오류 보고서를 큐에 넣습니다. 관리자 권한으로 로그인하는 경우 마지막으로 로그인한 이후에 발생한 모든 오류를 보고할 수 있습니다(오류 보고서를 3일마다 한 번 이상 보낼지 묻는 메시지는 표시되지 않음). `-errorreport` 옵션이 지정되지 않은 경우 기본 동작입니다.|
|`send`|내부 컴파일러 오류가 발생하고 컴퓨터 및 사용자 정책 설정에서 허용하는 경우 컴파일러는 데이터를 Microsoft로 보냅니다.<br /><br /> [Windows 오류 보고](/windows/desktop/wer/windows-error-reporting) 시스템 설정에서 보고 기능을 사용하도록 설정한 경우 `-errorreport:send` 옵션은 자동으로 Microsoft에 오류 정보를 전송하려고 시도합니다. |
|`none`|내부 컴파일러 오류가 발생하는 경우 오류를 수집하거나 Microsoft로 보내지 않습니다.|

컴파일러는 오류가 발생했을 때 스택을 포함하는 데이터를 보냅니다(일반적으로 일부 소스 코드가 포함됨). `-errorreport`를 [-bugreport](bugreport.md) 옵션과 함께 사용하는 경우 전체 소스 파일이 전송됩니다.

이 옵션은 [-bugreport](bugreport.md) 옵션과 함께 사용하는 것이 가장 좋습니다. Microsoft 엔지니어가 오류를 보다 쉽게 재현할 수 있기 때문입니다.

> [!NOTE]
> Visual Studio 개발 환경 내에서는 `-errorreport` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 코드는 `T2.vb`를 컴파일하려고 시도하고, 컴파일러에서 내부 컴파일러 오류가 발생하는 경우 오류 보고서를 Microsoft로 보낼지 묻는 메시지를 표시합니다.

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [-bugreport](bugreport.md)
