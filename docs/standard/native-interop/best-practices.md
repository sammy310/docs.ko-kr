---
title: 기본 상호 운용성 모범 사례 - .NET
description: .NET에서 기본 구성 요소와 인터페이스하는 모범 사례를 알아봅니다.
ms.date: 01/18/2019
ms.openlocfilehash: e5d96471e796dca712d25d2d9e2609508180d83f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391223"
---
# <a name="native-interoperability-best-practices"></a>기본 상호 운용성 모범 사례

.NET에서는 기본 상호 운용성 코드를 사용자 지정하는 다양한 방법을 제공합니다. 이 문서에는 Microsoft .NET 팀이 네이티브 상호 운용성을 위해 따르는 지침이 포함되어 있습니다.

## <a name="general-guidance"></a>일반 지침

이 섹션의 지침은 모든 interop 시나리오에 적용됩니다.

- ✔️ 호출하려는 네이티브 메서드와 동일한 명명 및 대문자 표시를 메서드와 매개 변수에 사용합니다.
- ✔️ 상수 값에 동일한 명명 및 대문자 표시를 사용하는 것이 좋습니다.
- ✔️ 네이티브 형식에 가장 가깝게 매핑되는 .NET 형식을 사용합니다. 예를 들어 C#에서 네이티브 형식이 `unsigned int`인 경우 `uint`를 사용합니다.
- ✔️ 기본 동작과 다른 동작을 원하는 경우에만 `[In]` 및 `[Out]` 특성을 사용합니다.
- ✔ 네이티브 배열 버퍼를 풀하려는 경우 <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType>을 사용하는 것이 좋습니다.
- ✔️ 네이티브 라이브러리와 동일한 이름 및 대문자 표시를 사용하여 P/Invoke 선언을 클래스에 래핑하는 것이 좋습니다.
  - 이렇게 하면 `[DllImport]` 특성이 C# `nameof` 언어 기능을 사용하여 네이티브 라이브러리의 이름을 전달하고 네이티브 라이브러리 이름의 철자가 잘못 입력되지 않았는지 확인할 수 있습니다.

## <a name="dllimport-attribute-settings"></a>DllImport 특성 설정

| 설정 | 기본값 | 권장 | 세부 정보 |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  기본값 유지  | 이 옵션을 명시적으로 false로 설정하면 실패한 HRESULT 반환 값이 예외로 바뀝니다(그 결과로 정의의 반환 값은 Null이 됨).|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | API에 따라 다름  | API에서 GetLastError를 사용하는 경우 이 옵션을 true로 설정하고, Marshal.GetLastWin32Error를 사용하여 값을 가져옵니다. API에서 오류가 있음을 나타내는 조건을 설정하는 경우 실수로 덮어쓰지 않도록 다른 호출을 수행하기 전에 오류를 가져옵니다.|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | `CharSet.None`(`CharSet.Ansi` 동작으로 대체됨)  | 정의에 문자열 또는 문자가 있는 경우 명시적으로 `CharSet.Unicode` 또는 `CharSet.Ansi` 사용 | 문자열의 마샬링 동작과 `false`인 경우 `ExactSpelling`에서 수행하는 작업을 지정합니다. `CharSet.Ansi`는 Unix에서 실제로 UTF8입니다. _대부분_의 경우 Windows에서는 유니코드, Unix에서는 UTF8이 사용됩니다. 자세한 내용은 [문자 집합 문서](./charset.md)를 참조하세요. |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | 이 옵션을 true로 설정하면 `CharSet` 설정 값(`CharSet.Ansi`는 “A”, `CharSet.Unicode`는 “W”)에 따라 “A” 또는 “W” 접미사가 있는 대체 함수 이름을 런타임이 찾지 않으므로 성능이 약간 향상됩니다. |

## <a name="string-parameters"></a>String 매개 변수

CharSet가 유니코드이거나 인수가 명시적으로 로 표시되고 문자열이 값으로 전달되는 경우(`ref` 또는 `out` 아님), 문자열이 고정되며 네이티브 코드에서 직접 사용됩니다(복사되지 않음).`[MarshalAs(UnmanagedType.LPWSTR)]` __

문자열을 명시적으로 ANSI 처리하려는 경우가 아니면, `[DllImport]`를 `Charset.Unicode`로 표시해야 합니다.

❌매개 변수를 사용하지 `[Out] string` 마십시오. `[Out]` 특성을 사용하여 값으로 전달된 문자열 매개 변수는 문자열이 인턴 지정된 문자열인 경우 런타임을 불안정하게 만들 수 있습니다. 문자열 인터닝에 대한 자세한 내용은 <xref:System.String.Intern%2A?displayProperty=nameWithType> 문서를 참조하세요.

❌매개 `StringBuilder` 변수를 방지합니다. `StringBuilder` 마샬링은 *항상* 네이티브 버퍼 복사본을 만듭니다. 따라서 매우 비효율적일 수 있습니다. 문자열을 사용하는 Windows API를 호출하는 일반적인 시나리오를 살펴보겠습니다.

1. 원하는 용량의 SB 만들기(관리되는 용량 할당)**{1}**
2. 호출
   1. 네이티브 버퍼 할당**{2}**
   2. `[In]` _(`StringBuilder` 매개 변수의 기본값)_ 인 경우 콘텐츠 복사
   3. `[Out]` **{3}** _(`StringBuilder`의 기본값)_ 인 경우 새로 할당된 관리형 배열에 네이티브 버퍼 복사
3. `ToString()`관리되는 또 다른 배열할당**{4}**

네이티브 *{4}* 코드에서 문자열을 가져옵니다 할당입니다. 이를 제한하는 가장 좋은 방법은 다른 호출에서 `StringBuilder`를 재사용하는 것이지만, 여전히 *1*개 할당만 저장됩니다. `ArrayPool`의 문자 버퍼를 사용하고 캐시하는 것이 훨씬 더 좋습니다. 그러면 후속 호출에서는 `ToString()`의 할당에만 바로 액세스할 수 있습니다.

`StringBuilder`의 다른 문제는 항상 반환 버퍼 백업을 첫 번째 Null에 복사하는 것입니다. 다시 전달된 문자열이 종료되지 않았거나 이중 Null 종료 문자열인 경우 P/Invoke가 올바르지 않습니다.

`StringBuilder`를 사용하는 경우 유의할 마지막 문제는 interop에 대해 항상 고려되는 숨겨진 Null이 용량에 포함되지 **않는**다는 것입니다.** 대부분의 API가 Null을 ‘포함’하는 버퍼 크기를 원하기 때문에 이 동작이 잘못 파악되는 경우가 많습니다.** 이로 인해 불필요한 할당이 발생할 수 있습니다. 또한 이 문제로 인해 런타임이 복사본 최소화를 위해 `StringBuilder` 마샬링을 최적화할 수 없게 됩니다.

✔️`ArrayPool`의 `char[]`을 사용하는 것이 좋습니다.

문자열 마샬링에 대한 자세한 내용은 [문자열의 기본 마샬링](../../framework/interop/default-marshaling-for-strings.md) 및 [문자열 마샬링 사용자 지정](customize-parameter-marshaling.md#customizing-string-parameters)을 참조하세요.

> __윈도우 특정__ 문자열의 `[Out]` 경우 CLR은 `CoTaskMemFree` 기본적으로 사용되며 무료 `SysStringFree` 문자열이나 로 `UnmanagedType.BSTR`표시된 문자열에 사용합니다.
> **출력 문자열 버퍼가 있는 대부분의 API의 경우:** 문자 수에서 전달된 문자 수에는 null이 포함되어야 합니다. 반환된 값이 전달된 문자 수보다 작으면 호출이 성공하고 값은 후행 Null이 ‘없는’ 문자 수가 됩니다.** 그렇지 않으면 개수는 Null 문자를 ‘포함’하는 필수 버퍼 크기입니다.**
>
> - 5에 통과, 4를 얻을 : 문자열은 후행 null로 긴 4 자입니다.
> - 5에 통과, 6을 얻을 : 문자열은 5 자 길이이며, null을 유지하기 위해 6 자 버퍼가 필요합니다.
> [문자열에 대한 Windows 데이터 형식](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a>부울 매개 변수 및 필드

부울은 문제가 발생하기 쉽습니다. 기본적으로 .NET `bool`은 4바이트 값인 Windows `BOOL`로 마샬링됩니다. 그러나 C 및 C++의 `_Bool` 및 `bool` 형식은 ‘1’바이트입니다.** 이로 인해 반환 값의 절반이 버려지고 ‘잠재적’으로 결과가 변경될 수 있기 때문에 버그를 추적하기 어려울 수 있습니다.** .NET `bool` 값을 C 또는 C++ `bool` 형식으로 마샬링하는 방법에 대한 자세한 내용은 [부울 필드 마샬링 사용자 지정](customize-struct-marshaling.md#customizing-boolean-field-marshaling) 문서를 참조하세요.

## <a name="guids"></a>GUIDs

GUID는 시그니처에 직접 사용할 수 있습니다. 많은 Windows API는 `REFIID`와 같은 `GUID&` 형식 별칭을 사용합니다. ref로 전달된 경우 `ref` 또는 `[MarshalAs(UnmanagedType.LPStruct)]` 특성으로 전달할 수 있습니다.

| GUID | by-ref GUID |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

❌GUID 매개 `[MarshalAs(UnmanagedType.LPStruct)]` 변수 이외의 `ref` 용도에는 사용하지 마십시오.

## <a name="blittable-types"></a>blittable 형식

blittable 형식은 관리 코드와 네이티브 코드에 동일한 비트 수준 표현이 있는 형식입니다. 따라서 네이티브 코드로(에서) 마샬링하기 위해 다른 형식으로 변환하지 않아도 되며, 이로 인해 성능이 향상되기 때문에 이 형식을 사용하는 것이 좋습니다.

**blittable 형식:**

- `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`
- blittable 형식의 비중첩 1차원 배열(예: `int[]`)
- 인스턴스 필드에 blittable 값 형식만 사용하는, 고정 레이아웃의 구조체 및 클래스
  - 고정 레이아웃에는 `[StructLayout(LayoutKind.Sequential)]` 또는 `[StructLayout(LayoutKind.Explicit)]`이 필요함
  - 구조체는 기본적으로 `LayoutKind.Sequential`이고, 클래스는 `LayoutKind.Auto`임

**비 blittable:**

- `bool`

**때때로 blittable**:

- `char`, `string`

blittable 형식이 참조로 전달된 경우 중간 버퍼에 복사되는 대신 마샬러에 의해 고정됩니다. 클래스는 본질적으로 참조로 전달되고, 구조체는 `ref` 또는 `out`과 함께 사용할 경우 참조로 전달됩니다.

`char`는 1차원 배열의 blittable이거나, 포함하는 형식의 일부인 경우 `[StructLayout]` 및 `CharSet = CharSet.Unicode`로 명시적으로 표시됩니다 **.**

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

`string`은 다른 형식에 포함되지 않고 `[MarshalAs(UnmanagedType.LPWStr)]`로 표시된 인수로 전달되거나 `[DllImport]`에 `CharSet = CharSet.Unicode`가 설정되어 있는 경우 blittable입니다.

고정 `GCHandle` 만들기를 시도하면 형식이 blittable인지 확인할 수 있습니다. 형식이 문자열이 아니거나 blittable로 간주되지 않는 경우 `GCHandle.Alloc`에서 `ArgumentException`이 throw됩니다.

✔️ 가능한 경우 구조체를 blittable로 설정합니다.

자세한 내용은 다음을 참조하세요.

- [Blittable 형식 및 비 Blittable 형식](../../framework/interop/blittable-and-non-blittable-types.md)
- [마샬링 유형](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a>관리형 개체를 활성 상태로 유지

`GC.KeepAlive()`는 KeepAlive 메서드가 적중될 때까지 개체가 범위 내에 유지되도록 합니다.

[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef)을 사용하면 마샬러가 P/호출 기간 동안 개체를 살아 있게 유지할 수 있습니다. 메서드 시그니처에 `IntPtr` 대신 사용할 수 있습니다. `SafeHandle`은 이 클래스를 효과적으로 대체하며 대신 사용되어야 합니다.

[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle)관리되는 개체를 고정하고 네이티브 포인터를 가져오는 것을 허용합니다. 기본 패턴은 다음과 같습니다.

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

고정은 `GCHandle`의 기본값이 아닙니다. 다른 주요 패턴은 네이티브 코드를 통해 관리형 개체에 대한 참조를 전달하고, 일반적으로 콜백을 사용하여 관리 코드에 다시 전달하기 위한 것입니다. 패턴은 다음과 같습니다.

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

메모리 누수를 방지하려면 `GCHandle`을 명시적으로 해제해야 합니다.

## <a name="common-windows-data-types"></a>일반적인 Windows 데이터 형식

Windows API에서 일반적으로 사용되는 데이터 형식과 Windows 코드를 호출할 때 사용할 C# 형식 목록은 다음과 같습니다.

다음 형식은 이름과 관계없이 32비트 및 64비트 Windows에서 동일한 크기입니다.

| 너비 | Windows          | C(Windows)          | C#       | 대체                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| 32    | `BOOL`           | `int`                | `int`    | `bool`                               |
| 8     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| 8     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| 8     | `CHAR`           | `char`               | `sbyte`  |                                      |
| 8     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| 16    | `SHORT`          | `short`              | `short`  |                                      |
| 16    | `CSHORT`         | `short`              | `short`  |                                      |
| 16    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| 16    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| 16    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| 32    | `INT`            | `int`                | `int`    |                                      |
| 32    | `LONG`           | `long`               | `int`    |                                      |
| 32    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| 32    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| 64    | `QWORD`          | `long long`          | `long`   |                                      |
| 64    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| 64    | `LONGLONG`       | `long long`          | `long`   |                                      |
| 64    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| 64    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| 32    | `HRESULT`        | `long`               | `int`    |                                      |
| 32    | `NTSTATUS`       | `long`               | `int`    |                                      |

다음 형식은 포인터로, 플랫폼의 너비를 따릅니다. 이러한 형식에는 `IntPtr`/`UIntPtr`을 사용합니다.

| 서명된 포인터 형식(`IntPtr` 사용) | 서명되지 않은 포인터 형식(`UIntPtr` 사용) |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

C `void*`인 Windows `PVOID`는 `IntPtr` 또는 `UIntPtr`로 마샬링할 수 있지만, 가능한 경우 `void*`를 사용하는 것이 좋습니다.

[Windows 데이터 형식](/windows/desktop/WinProg/windows-data-types)

[데이터 형식 범위](/cpp/cpp/data-type-ranges)

## <a name="structs"></a>구조체

관리형 구조체는 스택에 생성되며, 메서드가 반환될 때까지 제거되지 않습니다. 정의상, “고정”되며 GC에 의해 이동되지 않습니다. 네이티브 코드에서 현재 메서드의 끝을 지나 포인터를 사용하지 않는 경우에도 안전하지 않은 코드 블록의 주소를 사용하면 됩니다.

blittable 구조체는 마샬링 계층에서 직접 사용할 수 있으므로 성능이 훨씬 더 뛰어납니다. 구조체를 blittable로 설정합니다(예: `bool` 사용 안 함). 자세한 내용은 [blittable 형식](#blittable-types) 섹션을 참조하세요.

구조체가 blittable인 경우 성능 향상을 위해 `Marshal.SizeOf<MyStruct>()` 대신 `sizeof()`를 사용합니다.** 위에서 언급한 대로, 고정 `GCHandle` 만들기를 시도하여 형식이 blittable인지 확인할 수 있습니다. 형식이 문자열이 아니거나 blittable로 간주되지 않는 경우 `GCHandle.Alloc`에서 `ArgumentException`이 throw됩니다.

정의의 구조체 포인터는 `ref`에 의해 전달되거나 `unsafe` 및 `*`를 사용해야 합니다.

✔️ 공식 플랫폼 문서 또는 헤더에 사용되는 모양 및 이름에 최대한 가깝게 관리형 구조체를 일치시킵니다.

✔️ 성능 개선을 위해 blittable 구조체에 `Marshal.SizeOf<MyStruct>()` 대신 C# `sizeof()`를 사용합니다.

❌사용 `System.Delegate` 하거나 `System.MulticastDelegate` 필드를 사용 하지 마십시오 구조에서 함수 포인터 필드를 나타냅니다.

필수 <xref:System.Delegate?displayProperty=fullName> <xref:System.MulticastDelegate?displayProperty=fullName> 서명이 없기 때문에 전달된 대리자가 네이티브 코드가 기대하는 서명과 일치한다는 것을 보장하지 않습니다. 또한 .NET Framework 및 .NET Core에서 네이티브 표현을 포함 `System.Delegate` `System.MulticastDelegate` 하거나 관리 되는 개체에 해당 개체를 포함 하는 구조체를 마샬링 네이티브 표현에서 필드의 값이 관리 되는 대리자를 래핑 하는 함수 포인터 되지 않은 경우 런타임을 불안정 하 게 할 수 있습니다. .NET 5 및 이후 버전에서는 `System.Delegate` 네이티브 `System.MulticastDelegate` 표현에서 관리되는 개체로 또는 필드를 마샬링하는 것은 지원되지 않습니다. `System.Delegate` 또는 `System.MulticastDelegate`또는 의 특정 대리자 유형을 사용합니다.

### <a name="fixed-buffers"></a>고정 버퍼

`INT_PTR Reserved1[2]` 등의 배열을 두 개의 `IntPtr` 필드인 `Reserved1a` 및 `Reserved1b`로 마샬링해야 합니다. 네이티브 배열이 기본 형식인 경우 `fixed` 키워드를 사용하여 보다 명확하게 작성할 수 있습니다. 예를 들어 `SYSTEM_PROCESS_INFORMATION`은 네이티브 헤더에서 다음과 같습니다.

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

C#에서는 다음과 같이 작성할 수 있습니다.

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

그러나 고정 버퍼에는 몇 가지 문제가 있습니다. 비 blittable 형식의 고정 버퍼는 올바르게 마샬링되지 않으므로, 현재 위치 배열을 여러 개의 개별 필드로 확장해야 합니다. 또한 .NET Framework 및 .NET Core 3.0 이전 버전에서 고정 버퍼 필드가 포함된 구조체를 비 blittable 구조체 내에 중첩하면 고정 버퍼 필드는 네이티브 코드로 올바르게 마샬링되지 않습니다.
