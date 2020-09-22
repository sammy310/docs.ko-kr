---
title: 설치된 .NET Framework 버전 확인
description: 코드, regedit.exe 또는 PowerShell을 사용하여 Windows 레지스트리를 쿼리하는 방법으로 컴퓨터에 설치된 .NET Framework 버전을 검색합니다.
ms.date: 02/03/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: accc85f04514822233bc5df3a76eb99775fee529
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553742"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>방법: 설치된 .NET Framework 버전 확인

사용자는 자신의 컴퓨터에 여러 버전의 .NET Framework를 [설치](../install/index.md)하여 실행할 수 있습니다. 따라서 앱을 개발하거나 배포할 때는 사용자의 컴퓨터에 어떤 .NET Framework 버전이 설치되었는지 알아야 합니다. 레지스트리에는 컴퓨터에 설치된 .NET Framework 버전 목록이 포함되어 있습니다.

.NET Framework는 각 버전으로 식별되는 다음과 같은 2개의 주요 구성 요소로 구성됩니다.

- 앱의 기능을 제공하는 형식 및 리소스 컬렉션에 해당하는 어셈블리 집합. .NET Framework와 어셈블리는 동일한 버전 번호를 공유합니다. 예를 들어, .NET Framework 버전에는 4.5, 4.6.1, 4.7.2가 있습니다.

- 앱 코드를 관리하고 실행하는 CLR(공용 언어 런타임). 하나의 CLR 버전이 여러 개의.NET Framework 버전을 지원합니다. 예를 들어 CLR 버전이 4.0.30319.‘xxxxx’이고 ‘xxxxx’가 42000보다 작은 경우 .NET Framework 버전 4~4.5.2를 지원합니다.  CLR 버전이 4.0.30319.42000보다 크거나 같으면 .NET Framework 4.6 이상 버전의 .NET Framework를 지원합니다.

커뮤니티에서 유지 관리되는 도구를 사용하여 설치된 .NET Framework 버전을 확인할 수 있습니다.

- [https://github.com/jmalarcon/DotNetVersions](https://github.com/jmalarcon/DotNetVersions)

  .NET 2.0 명령줄 도구

- [https://github.com/EliteLoser/DotNetVersionLister](https://github.com/EliteLoser/DotNetVersionLister)

  PowerShell 2.0 모듈

.NET Framework의 버전별로 설치된 업데이트를 검색하는 방법에 대한 자세한 내용은 [방법: 설치된 .NET Framework 업데이트 확인](how-to-determine-which-net-framework-updates-are-installed.md).

## <a name="detect-net-framework-45-and-later-versions"></a>.NET Framework 4.5 이상 버전 검색

컴퓨터에 설치된 .NET Framework 버전(4.5 이상)은 레지스트리에서 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**에 나와 있습니다. **Full** 하위 키가 없으면 .NET Framework 4.5 이상이 설치되지 않은 것입니다.

> [!NOTE]
> 레지스트리 경로에서 **NET Framework Setup** 하위 키는 마침표로 시작되지 ‘않습니다’.

레지스트리의 **Release** REG_DWORD 값은 설치된 .NET Framework 버전을 나타냅니다.

<a name="version_table"></a>

| .NET Framework 버전 | **Release** 값 |
| ---------------------- | -------------------------- |
| .NET Framework 4.5     | 모든 Windows 운영 체제: 378389 |
| .NET Framework 4.5.1   | Windows 8.1 및 Windows Server 2012 R2: 378675<br />다른 모든 Windows 운영 체제: 378758 |
| .NET Framework 4.5.2   | 모든 Windows 운영 체제: 379893 |
| .NET Framework 4.6     | Windows 10: 393295<br />다른 모든 Windows 운영 체제: 393297 |
| .NET Framework 4.6.1   | Windows 10 11월 업데이트 운영 체제: 394254<br />다른 모든 Windows 운영 체제(Windows 10 포함): 394271 |
| .NET Framework 4.6.2   | Windows 10 1주년 업데이트 및 Windows Server 2016: 394802<br />다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 394806 |
| .NET Framework 4.7     | Windows 10 Creators Update: 460798<br />다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 460805 |
| .NET Framework 4.7.1   | Windows 10 Fall Creators Update 및 Windows Server, 버전 1709: 461308<br/>다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 461310 |
| .NET Framework 4.7.2   | Windows 10 2018년 4월 업데이트 및 Windows Server, 버전 1803: 461808<br/>Windows 10 2018년 4월 업데이트 및 Windows Server, 버전 1803 이외의 모든 Windows 운영 체제: 461814 |
| .NET Framework 4.8     | Windows 10 2019년 5월 업데이트 및 Windows 10 2019년 11월 업데이트: 528040<br/>Windows 10 2020년 5월 업데이트: 528372<br/>다른 모든 Windows 운영 체제(다른 Windows 10 운영 체제 포함): 528049 |

### <a name="minimum-version"></a>최소 버전

‘최소’ 버전의 .NET Framework가 있는지 확인하려면 이전 표에서 해당 버전의 가장 작은 **Release** REG_DWORD 값을 사용하세요.

예를 들어 애플리케이션이 .NET Framework 4.8 이상 버전에서 실행되는 경우 528040과 같거나 이보다 큰 **Release** REG_DWORD 값을 테스트합니다.

| .NET Framework 버전 | 최소값 |
| ---------------------- | ------------- |
| .NET Framework 4.5     | 378389 |
| .NET Framework 4.5.1   | 378675 |
| .NET Framework 4.5.2   | 379893 |
| .NET Framework 4.6     | 393295 |
| .NET Framework 4.6.1   | 394254 |
| .NET Framework 4.6.2   | 394802 |
| .NET Framework 4.7     | 460798 |
| .NET Framework 4.7.1   | 461308 |
| .NET Framework 4.7.2   | 461808 |
| .NET Framework 4.8     | 528040 |

### <a name="use-registry-editor"></a>레지스트리 편집기 사용

01. **시작** 메뉴에서 **실행**을 선택하고 *regedit*을 입력한 다음, **OK**를 선택합니다.

    regedit을 실행하려면 관리자 자격 증명이 있어야 합니다.

01. 레지스트리 편집기에서 다음 하위 키를 엽니다. **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**. **전체**하위 키가 없으면 .NET Framework 4.5 이상이 설치되어 있지 않은 것입니다.

01. **Release**라는 REG_DWORD 항목을 확인합니다. 릴리스 DWORD가 있으면 컴퓨터에 .NET Framework 4.5 이상이 설치된 것입니다. 해당 값은 .NET Framework의 특정 버전에 해당합니다. 예를 들어 다음 그림에서**Release** 항목의 값은 528040으로, 이것은 .NET Framework 4.8의 릴리스 키입니다.

    ![.NET Framework 4.5.에 대한 레지스트리 항목](./media/clr-installdir.png ".NET Framework 4.5.에 대한 레지스트리 항목")

### <a name="use-powershell-to-check-for-a-minimum-version"></a>PowerShell을 사용하여 최소 버전 확인

PowerShell 명령을 사용하여 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** 하위 키의 **Release** 항목값을 확인합니다.

다음 예제에서는 **릴리스** 항목 값을 확인하여 .NET Framework 4.6.2 이상이 설치되어 있는지 확인합니다. 설치된 경우 `True` 코드 반환, 설치되지 않은 경우 `False` 코드 반환.

```powershell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

### <a name="query-the-registry-using-code"></a>코드를 사용하여 레지스트리를 쿼리

01. <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> 및 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> 메서드를 사용하여 Windows 레지스트리의 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full** 하위 키에 액세스합니다.

    > [!IMPORTANT]
    > 실행 중인 앱이 32비트이고 64비트 Windows에서 실행되는 경우 레지스트리 경로는 이전에 나열된 것과 다릅니다. 64비트 레지스트리는 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** 하위 키에서 사용할 수 있습니다. 예를 들어 .NET Framework 4.5의 레지스트리 하위 키는 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**입니다.

01. **Release** REG_DWORD 값을 확인하여 설치된 버전을 확인합니다. 이후 버전과의 호환성을 유지하려는 경우 버전의 값이 [.NET Framework 버전 표](#version_table)에 나와 있는 값 이상인지를 확인하면 됩니다.

다음 예제에서는 레지스트리에서 **릴리스** 항목값을 확인하여 .NET Framework 4.5 이상 버전이 설치되어 있는지 확인합니다.

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

이 예제에서는 버전을 확인하기 위한 권장된 방법을 수행합니다.

- **릴리스**항목의 값이 알려진 릴리스 키의 값보다 *크거나 같은지* 확인합니다.
- 최신 버전에서 가장 오래된 버전 순서대로 확인합니다.

## <a name="detect-net-framework-10-through-40"></a>.NET Framework 1.0~4.0 검색

1\.1에서 4.0까지의 각 .NET Framework 버전은 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP**의 하위 키로 표시됩니다. 다음 표에서는 각 .NET Framework 버전의 경로를 에 나열합니다. 대부분 버전의 **Install** REG_DWORD 값은 `1`이고, 이는 해당 버전이 설치되었음을 나타냅니다. 이러한 하위 키에는 버전 문자열을 포함하는 **Version** REG_SZ 값도 있습니다.

> [!NOTE]
> 레지스트리 경로에서 **NET Framework Setup** 하위 키는 마침표로 시작되지 ‘않습니다’.

| 프레임워크 버전  | 레지스트리 하위 키 | 값 |
| ------------------ | --------------- | ----- |
| 1.0                | **HKLM\\Software\\Microsoft\\.NETFramework\\Policy\\v1.0\\3705**     | **Install** REG_SZ가 `1`과 같음 |
| 1.1                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v1.1.4322**   | **Install** REG_DWORD가 `1`과 같음 |
| 2.0                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v2.0.50727**  | **Install** REG_DWORD가 `1`과 같음 |
| 3.0                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.0\\Setup** | **InstallSuccess** REG_DWORD가 `1`과 같음 |
| 3.5                | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v3.5**        | **Install** REG_DWORD가 `1`과 같음 |
| 4.0 클라이언트 프로필 | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Client**  | **Install** REG_DWORD가 `1`과 같음 |
| 4.0 전체 프로필   | **HKLM\\Software\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full**    | **Install** REG_DWORD가 `1`과 같음 |

> [!IMPORTANT]
> 실행 중인 앱이 32비트이고 64비트 Windows에서 실행되는 경우 레지스트리 경로는 이전에 나열된 것과 다릅니다. 64비트 레지스트리는 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** 하위 키에서 사용할 수 있습니다. 예를 들어 .NET Framework 3.5의 레지스트리 하위 키는 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**입니다.

.NET Framework 1.0 하위 키의 레지스트리 경로는 다른 하위 키와 다릅니다.

### <a name="use-registry-editor-older-framework-versions"></a>레지스트리 편집기 사용(이전 프레임워크 버전)

01. **시작** 메뉴에서 **실행**을 선택하고 *regedit*을 입력한 다음, **OK**를 선택합니다.

    regedit을 실행하려면 관리자 자격 증명이 있어야 합니다.

01. 확인하려는 버전과 일치하는 하위 키를 엽니다. [.NET Framework 1.0~4.0 검색](#detect-net-framework-10-through-40) 섹션의 표를 사용합니다.

    다음 그림은 .NET Framework 3.5의 하위 키와 **Version** 값을 보여줍니다.

    ![.NET Framework 3.5에 대한 레지스트리 항목](./media/net-4-and-earlier.png ".NET Framework 3.5 및 이전 버전")

### <a name="query-the-registry-using-code-older-framework-versions"></a>코드를 사용한 레지스트리 쿼리(이전 프레임워크 버전)

<xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> 클래스를 사용하여 Windows 레지스트리의**HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP** 하위 키에 액세스합니다.

> [!IMPORTANT]
> 실행 중인 앱이 32비트이고 64비트 Windows에서 실행되는 경우 레지스트리 경로는 이전에 나열된 것과 다릅니다. 64비트 레지스트리는 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\** 하위 키에서 사용할 수 있습니다. 예를 들어 .NET Framework 3.5의 레지스트리 하위 키는 **HKEY_LOCAL_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\NET Framework Setup\\NDP\\v3.5**입니다.

다음 예제에서는 설치된 .NET Framework 1~4 버전을 찾습니다.

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a>CLR 버전 찾기

.NET Framework와 함께 설치된 .NET Framework CLR은 별도로 버전이 지정됩니다. .NET Framework CLR의 버전을 검색하는 두 가지 방법은 다음과 같습니다.

- **Clrver.exe 도구**

  [CLR 버전 도구(Clrver.exe)](../tools/clrver-exe-clr-version-tool.md)를 사용하여 컴퓨터에 설치된 CRL의 버전을 확인합니다. [Visual Studio용 개발자 명령 프롬프트](../tools/developer-command-prompt-for-vs.md)를 열고 `clrver`를 입력합니다.

  샘플 출력:

  ```console
  Versions installed on the machine:
  v2.0.50727
  v4.0.30319
  ```

- **`Environment` 클래스**

  > [!IMPORTANT]
  > .NET Framework 4.5 이상 버전의 경우 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 속성을 사용하여 CLR의 버전을 확인하지 않습니다. 대신 [.NET Framework 4.5 이상 버전 검색](#detect-net-framework-45-and-later-versions)에 설명된 대로 레지스트리를 쿼리합니다.
  
  01. <xref:System.Version>개체를 검색하기 위해 <xref:System.Environment.Version?displayProperty=nameWithType>속성을 쿼리합니다.
  
      반환된 `System.Version`개체는 현재 코드를 실행하는 런타임 버전을 식별합니다. 컴퓨터에 설치된 어셈블리 버전이나 다른 런타임 버전은 반환하지 않습니다.
  
      .NET Framework 버전 4, 4.5, 4.5.1 및 4.5.2의 경우 반환된 <xref:System.Version> 개체 문자열 표현은 4.0.30319.‘xxxxx’ 형식이며, ‘xxxxx’는 42000보다 작습니다.  .NET Framework 4.6 및 이후 버전의 경우 형식은 4.0.30319.42000입니다.
  
  01. **Version** 개체를 가져온 후, 다음과 같이 개체를 쿼리합니다.
  
      - 주 릴리스 식별자(예:버전 4.0의 경우 *4*)는 <xref:System.Version.Major%2A?displayProperty=nameWithType>속성을 사용합니다.
  
      - 부 릴리스 식별자(예:버전 4.0의 경우 *0*)는 <xref:System.Version.Minor%2A?displayProperty=nameWithType>속성을 사용합니다.
  
      - 전체 버전 문자열(예를 들어*4.0.30319.18010*)에는 <xref:System.Version.ToString%2A?displayProperty=nameWithType>메서드를 사용합니다. 메서드는 코드를 실행 하는 런타임 버전을 반영하는 단일 값을 반환합니다. 이는 컴퓨터에 설치된 어셈블리 버전이나 다른 런타임 버전은 반환하지 않습니다.

  다음 예제에서는 <xref:System.Environment.Version%2A?displayProperty=nameWithType>속성을 사용하여 CLR 버전 정보를 검색합니다.
  
  [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
  [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>참조

- [방법: 설치된 .NET Framework 업데이트 확인](how-to-determine-which-net-framework-updates-are-installed.md)
- [개발자용 .NET Framework 설치](../install/guide-for-developers.md)
- [.NET Framework 버전 및 종속성](versions-and-dependencies.md)
