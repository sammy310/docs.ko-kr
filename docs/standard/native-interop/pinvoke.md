---
title: P/Invoke(플랫폼 호출)
description: .NET에서 P/Invoke를 통해 네이티브 함수를 호출하는 방법을 알아봅니다.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 4836096e12f6c3d317daa5da91566ab472053ede
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409239"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="b6759-103">P/Invoke(플랫폼 호출)</span><span class="sxs-lookup"><span data-stu-id="b6759-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="b6759-104">P/Invoke는 관리 코드에서 비관리형 라이브러리의 구조체, 콜백 및 함수에 액세스할 수 있는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="b6759-105">P/Invoke API는 대부분 `System` 및 `System.Runtime.InteropServices`라는 두 네임스페이스에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="b6759-106">이러한 두 네임스페이스를 사용하면 기본 구성 요소와 통신하는 방법을 설명하는 도구가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="b6759-107">관리 코드에서 관리되지 않는 함수를 호출하는 가장 일반적인 예제에서 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="b6759-108">명령줄 애플리케이션에서 메시지 상자를 표시하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-108">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="b6759-109">앞의 예제는 간단하지만 관리 코드에서 관리되지 않는 함수를 호출하는 데 필요한 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="b6759-110">예제를 단계별로 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="b6759-111">줄 #1에서는 필요한 항목이 모두 포함되어 있는 `System.Runtime.InteropServices` 네임스페이스에 대한 using 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="b6759-112">줄 #7에서는 `DllImport` 특성을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="b6759-113">이 특성은 관리되지 않는 DLL을 로드하도록 런타임에 지정하므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="b6759-114">전달된 문자열은 대상 함수가 있는 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-114">The string passed in is the DLL our target function is in.</span></span>
*   <span data-ttu-id="b6759-115">줄 #8은 P/Invoke 작업의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-115">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="b6759-116">관리되지 않는 메서드와 **동일한 시그니처**가 있는 관리되는 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-116">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="b6759-117">선언에서 확인할 수 있는 새 키워드 `extern`은 이 메서드가 외부 메서드이며 호출 시 런타임이 `DllImport` 특성에 지정된 DLL에서 찾도록 런타임에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-117">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="b6759-118">예제의 나머지 부분에서는 단순히 다른 관리되는 메서드와 마찬가지로 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-118">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="b6759-119">macOS에 대한 샘플도 이와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-119">The sample is similar for macOS.</span></span> <span data-ttu-id="b6759-120">macOS에서는 다른 동적 라이브러리 명명 체계를 사용하므로 `DllImport` 특성의 라이브러리 이름을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-120">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="b6759-121">다음 샘플에서는 `getpid(2)` 함수를 사용하여 애플리케이션의 프로세스 ID를 가져오고 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-121">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="b6759-122">Linux에서도 이와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-122">It is also similar on Linux.</span></span> <span data-ttu-id="b6759-123">`getpid(2)`는 표준 [POSIX](https://en.wikipedia.org/wiki/POSIX) 시스템 호출이기 때문에 함수 이름이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-123">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="b6759-124">비관리 코드에서 관리 코드 호출</span><span class="sxs-lookup"><span data-stu-id="b6759-124">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="b6759-125">런타임에서 양방향 통신을 허용하므로 함수 포인터를 사용하여 네이티브 함수에서 관리 코드로 콜백할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-125">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="b6759-126">관리 코드에서 함수 포인터와 가장 가까운 것은 **대리자**이므로, 대리자를 사용하여 네이티브 코드에서 관리 코드로의 콜백을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-126">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="b6759-127">이 기능을 사용하는 방법은 앞에서 설명한 관리 코드에서 네이티브 코드로의 프로세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-127">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="b6759-128">지정된 콜백에 대해 시그니처와 일치하는 대리자를 정의하고 외부 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-128">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="b6759-129">다른 모든 작업은 런타임에서 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-129">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="b6759-130">예제를 살펴보기 전에 작업해야 하는 관리되지 않는 함수의 시그니처를 검토하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-130">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="b6759-131">모든 창을 열거하기 위해 호출할 함수에는 다음과 같은 시그니처가 있습니다. `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="b6759-131">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="b6759-132">첫 번째 매개 변수는 콜백입니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-132">The first parameter is a callback.</span></span> <span data-ttu-id="b6759-133">이 콜백에는 다음과 같은 시그니처가 있습니다. `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="b6759-133">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="b6759-134">이제 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-134">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="b6759-135">예제의 줄 #9에서는 비관리 코드의 콜백 시그니처와 일치하는 대리자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-135">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="b6759-136">관리 코드에서 `IntPtr`을 사용하여 LPARAM 및 HWND 형식을 나타내는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-136">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="b6759-137">줄 #13 및 #14에서는 user32.dll 라이브러리의 `EnumWindows` 함수를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-137">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="b6759-138">줄 #17-20에서는 대리자를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-138">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="b6759-139">이 간단한 예제에서는 단순히 핸들을 콘솔에 출력하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-139">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="b6759-140">마지막으로, 줄 #24에서는 외부 메서드를 호출하고 대리자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-140">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="b6759-141">Linux 및 macOS 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-141">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="b6759-142">해당 예제에서는 C 라이브러리 `libc`에 있는 `ftw` 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-142">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="b6759-143">이 함수는 디렉터리 계층 구조를 트래버스하는 데 사용되며, 함수에 대한 포인터를 해당 매개 변수 중 하나로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-143">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="b6759-144">이 함수에는 다음과 같은 시그니처가 있습니다. `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="b6759-144">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="b6759-145">macOS 예제에서는 동일한 함수를 사용하며, macOS에서 `libc`가 다른 위치에 유지되므로 `DllImport` 특성에 대한 인수만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-145">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="b6759-146">앞의 두 예제에서는 매개 변수를 사용하며, 두 경우 모두 매개 변수가 관리형 형식으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-146">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="b6759-147">런타임에서 “올바른 작업”을 수행하고 다른 쪽의 해당 항목으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-147">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="b6759-148">[형식 마샬링](type-marshalling.md) 페이지에서 형식이 네이티브 코드로 마샬링되는 방식을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-148">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>


## <a name="more-resources"></a><span data-ttu-id="b6759-149">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="b6759-149">More resources</span></span>

*   <span data-ttu-id="b6759-150">[PInvoke.net wiki](https://www.pinvoke.net/)는 일반적인 Windows API 및 호출 방법에 대한 정보가 포함된 우수한 Wiki입니다.</span><span class="sxs-lookup"><span data-stu-id="b6759-150">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Windows APIs and how to call them.</span></span>
*   [<span data-ttu-id="b6759-151">MSDN의 P/Invoke</span><span class="sxs-lookup"><span data-stu-id="b6759-151">P/Invoke on MSDN</span></span>](/cpp/dotnet/native-and-dotnet-interoperability)
*   [<span data-ttu-id="b6759-152">P/Invoke에 대한 Mono 설명서</span><span class="sxs-lookup"><span data-stu-id="b6759-152">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
