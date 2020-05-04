---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793543"
---
# <a name="-bugreport"></a>-bugreport

버그 보고서를 작성할 때 사용할 수 있는 파일을 만듭니다.

## <a name="syntax"></a>구문

```console
-bugreport:file
```

## <a name="arguments"></a>인수

|용어|정의|
|---|---|
|`file`|필수 요소. 버그 보고서를 포함할 파일의 이름입니다. 파일 이름에 공백이 있으면 이름을 따옴표(" ")로 묶습니다.|

## <a name="remarks"></a>설명

`file`에 추가되는 정보는 다음과 같습니다.

- 컴파일에 포함된 모든 소스 코드 파일의 복사본.

- 컴파일에 사용된 컴파일러 옵션의 목록.

- 컴파일러, 공용 언어 런타임 및 운영 체제에 대한 버전 정보.

- 컴파일러 출력입니다(있는 경우).

- 메시지가 표시된 문제에 대한 설명.

- 오류 메시지가 표시된 문제 해결 방법에 대한 설명.

모든 소스 코드 파일의 복사본이 `file`에 포함되기 때문에 최대한 짧은 프로그램으로 의심스러운 코드 결함을 재현하는 것이 좋습니다.

> [!IMPORTANT]
> `-bugreport` 옵션은 잠재적으로 중요한 정보를 포함하는 파일을 생성합니다. 여기에는 현재 시간, 컴파일러 버전, .NET Framework 버전, OS 버전, 사용자 이름, 컴파일러를 실행한 명령줄 인수, 모든 소스 코드, 참조된 어셈블리의 이진 형식 등이 포함됩니다. ASP.NET 애플리케이션의 서버 쪽 컴파일에 대한 Web.config 파일에서 명령줄 옵션을 지정하여 이 옵션에 액세스할 수 있습니다. 이를 방지하려면 사용자가 서버에서 컴파일하지 못하도록 Machine.config 파일을 수정합니다.

이 옵션을 `-errorreport:prompt`, `-errorreport:queue` 또는 `-errorreport:send`와 함께 사용할 때 애플리케이션에서 내부 컴파일러 오류가 발생하는 경우 `file`의 정보가 Microsoft로 전송됩니다. 이 정보는 Microsoft 엔지니어가 오류의 원인을 파악하는 데 도움이 되며 Visual Basic의 다음 릴리스를 개선하는 데 도움이 될 수 있습니다. 기본적으로 어떠한 정보도 Microsoft로 보내지 않습니다. 그러나 기본적으로 사용하도록 설정되는 `-errorreport:queue`를 사용하여 애플리케이션을 컴파일하면 애플리케이션이 해당 오류 보고서를 수집합니다. 그러면 컴퓨터의 관리자가 로그인할 때 오류 보고 시스템에 관리자가 로그온 이후 발생한 모든 오류 보고서를 Microsoft에 전달할 수 있는 팝업 창이 표시됩니다.

> [!NOTE]
> Visual Studio 개발 환경에서는 `-bugreport` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 *T2.vb*를 컴파일하고 *Problem.txt* 파일에 모든 버그 보고 정보를 저장합니다.

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a>참조

- [Visual Basic 명령줄 컴파일러](index.md)
- [-debug(Visual Basic)](debug.md)
- [-errorreport](errorreport.md)
- [샘플 컴파일 명령줄](sample-compilation-command-lines.md)
- [trustLevel Element for securityPolicy(ASP.NET 설정 스키마)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))
