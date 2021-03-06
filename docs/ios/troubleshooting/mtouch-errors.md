---
title: Xamarin.iOS 오류
description: 이 문서에서는 mtouch를 Xamarin.iOS 응용 프로그램을 번들로 사용 되는 도구에서 생성 한 다양 한 오류를 설명 합니다. 오류 코드에 의해 나열 되 고 전체 설명을 제공 합니다.
ms.topic: troubleshooting
ms.prod: xamarin
ms.assetid: 9F76162B-D622-45DA-996B-2FBF8017E208
ms.technology: xamarin-ios
author: lobrien
ms.author: laobri
ms.date: 03/06/2018
ms.openlocfilehash: a9d7f1eb0051035d6bfcc47e18fb0bdd00b60f5d
ms.sourcegitcommit: 4859da8772dbe920fdd653180450e5ddfb436718
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2018
ms.locfileid: "50235118"
---
# <a name="xamarinios-errors"></a>Xamarin.iOS 오류

## <a name="mt0xxx-mtouch-error-messages"></a>MT0xxx: mtouch 오류 메시지

예: 매개 변수, 환경, 도구 누락입니다.

<!--
 MT0xxx mtouch itself, e.g. parameters, environment (e.g. missing tools)
 https://github.com/xamarin/xamarin-macios/blob/master/tools/mtouch/error.cs
    -->

<a name="MT0000" />

### <a name="mt0000-unexpected-error---please-fill-a-bug-report-at-httpsgithubcomxamarinxamarin-maciosissuesnew"></a>MT0000: 예기치 않은 오류-에서 버그 보고서를 작성 하세요 https://github.com/xamarin/xamarin-macios/issues/new

예기치 않은 오류가 발생 했습니다. 하세요 [버그 보고서](https://github.com/xamarin/xamarin-macios/issues/new) 최대한 많은 정보를 포함 합니다.

* 전체 최대의 자세한 정도 사용 하 여 로그를 빌드합니다 (예: `-v -v -v -v` 에 **추가 mtouch 인수**);
* 오류를 재현 하는 최소한의 테스트 사례 및
* 모든 버전 정보

정확한 버전 정보를 얻을 수는 가장 쉬운 방법은 사용 하는 것을 **Mac 용 Visual Studio** 메뉴에서 **Mac 용 Visual Studio에 대 한** 항목인 **자세한 정보 표시** 단추 및 복사/붙여넣기를 버전 정보 (사용할 수는 **복사 정보** 단추).

<a name="MT0001" />

### <a name="mt0001--devname-was-provided-without-any-device-specific-action"></a>MT0001: '-devname' 장치별 개입 없이 제공한

이 경고-devname mtouch 때 없는 장치 특정 작업에 전달 되 면 내보내집니다입니다 (-logdev/installdev/killdev/launchdev /-listapps) 요청 되었습니다.

<a name="MT0002" />

### <a name="mt0002-could-not-parse-the-environment-variable-"></a>MT0002: 환경 변수를 구문 분석할 수 없습니다 *.

잘못 된 환경 키를 설정 하려고 하면이 오류는 발생 = 변수 값 쌍입니다. 올바른 형식은 다음과 같습니다. `mtouch --setenv=VARIABLE=VALUE`

<a name="MT0003" />

### <a name="mt0003-application-name-exe-conflicts-with-an-sdk-or-product-assembly-dll-name"></a>MT0003: 응용 프로그램 이름 ' *.exe ' SDK 또는 제품 어셈블리 (.dll) 이름과 충돌 합니다.

실행 가능한 어셈블리의 이름과 응용 프로그램의 앱에서 모든 dll 이름과 일치할 수 없습니다. 실행 파일의 이름을 수정 하십시오.

<a name="MT0004" />

### <a name="mt0004-new-refcounting-logic-requires-sgen-to-be-enabled-too"></a>MT0004: 새 refcounting 논리 SGen 너무 사용 하도록 설정 해야 합니다.

Refcounting 확장을 사용 하도록 설정 하면 프로젝트의 iOS 빌드 옵션 (고급 탭)에서 SGen 가비지 수집기 설정할 수도 있습니다.

이 요구 사항은 7.2.1 Xamarin.iOS를 사용 하 여 시작 리프트 된, Boehm와 SGen 가비지 수집기를 사용 하 여 새 refcounting 논리를 사용할 수 있습니다.

<a name="MT0005" />

### <a name="mt0005-the-output-directory--does-not-exist"></a>MT0005: 출력 디렉터리 * 존재 하지 않습니다.

디렉터리를 만드세요.

이 오류는 더 이상 발생 하지 않습니다, mtouch는 존재 하지 않는 경우에 자동으로 디렉터리를 만듭니다.

<a name="MT0006" />

### <a name="mt0006-there-is-no-devel-platform-at--use---platformplat-to-specify-the-sdk"></a>MT0006: 없음 개발자 플랫폼에는 *를 사용-플랫폼 SDK를 지정 하는 구획 =.

Xamarin.iOS는 오류 메시지에 언급 된 위치에 SDK 디렉터리를 찾을 수 없습니다. 경로가 정확한 지 확인 하세요.

<a name="MT0007" />

### <a name="mt0007-the-root-assembly--does-not-exist"></a>MT0007: 루트 어셈블리 * 존재 하지 않습니다.

Xamarin.iOS는 오류 메시지에 언급 된 위치에서 어셈블리를 찾을 수 없습니다. 경로가 정확한 지 확인 하세요.

<a name="MT0008" />

### <a name="mt0008-you-should-provide-one-root-assembly-only-found--assemblies-"></a>MT0008: 제공 해야 하나 루트 어셈블리에 있는 # 어셈블리: *.

하나의 루트 어셈블리 있을 수 있지만 둘 이상의 루트 어셈블리 mtouch, 전달 되었습니다.

<a name="MT0009" />

### <a name="mt0009-error-while-loading-assemblies-"></a>MT0009: 어셈블리를 로드 하는 동안 오류: *.

루트 어셈블리 참조를 어셈블리를 로드 하는 동안 오류가 발생 했습니다. 자세한 내용은 빌드 출력에 제공 될 수 있습니다.

<a name="MT0010" />

### <a name="mt0010-could-not-parse-the-command-line-arguments-"></a>MT0010: 명령줄 인수 구문 분석 하지 못했습니다: *.

명령줄 인수 구문 분석 하는 동안 오류가 발생 했습니다. 그 설정이 모두 정확한 지 확인 하세요.

<a name="MT0011" />

### <a name="mt0011--was-built-against-a-more-recent-runtime--than-monotouch-supports"></a>MT0011: * MonoTouch 지 원하는 것 보다 더 최신 런타임 (*)에 대해 빌드된 합니다.

이 경고는 프로젝트에 Xamarin.iOS BCL을 사용 하 여 작성 되지 않았습니다 하는 클래스 라이브러리에 대 한 참조 하기 때문에 일반적으로 보고 됩니다.

.NET 4.0 SDK를 사용 하는 앱만.NET 2.0을 지 원하는 시스템에서 작동 하지 않을 동일한 방식으로.NET 4.0을 사용 하 여 빌드된 라이브러리 Xamarin.iOS에서 작동 하지 않을 수, Xamarin.iOS에서 표시 되지 않는 API를 사용할 수 있습니다.

일반 방법은 Xamarin.iOS 클래스 라이브러리와 라이브러리를 빌드하는 것입니다. 이 새 Xamarin.iOS 클래스 라이브러리 프로젝트를 만들어 수행할 수 있으며 모든 원본 파일을 추가 합니다. 라이브러리의 소스 코드가 없는 경우 공급 업체에 문의 하 고 해당 라이브러리의 Xamarin.iOS 호환 버전을 제공 하는 요청 해야 합니다.

<a name="MT0012" />

### <a name="mt0012-incomplete-data-is-provided-to-complete-"></a>MT0012: 불완전 한 데이터가 완료 제공 *.

이 오류는 xamarin.ios 현재 버전에서 더 이상 보고 되지 않습니다.

<a name="MT0013" />

### <a name="mt0013-profiling-support-requires-sgen-to-be-enabled-too"></a>MT0013: 프로 파일링 지원 하려면 필요 sgen 너무 사용 하도록 설정 합니다.

SGen (-sgen) 프로 파일링 하는 경우에 사용할 수 있어야 합니다 (-프로 파일링) 사용 가능 합니다.

<a name="MT0014" />

### <a name="mt0014-the-ios--sdk-does-not-support-building-applications-targeting-"></a>MT0014: iOS * SDK 대상으로 하는 응용 프로그램 빌드를 지원 하지 않습니다 * 합니다.

이 작업은 다음과 같은 경우에 발생할 수 있습니다.

*  ARMv6 사용 하도록 설정 하 고 Xcode 4.5 이상이 설치 됩니다.
*  ARMv7s 사용 하도록 설정 하 고 4.4 이상 이전 Xcode 설치 됩니다.

설치 된 버전의 Xcode에 선택한 아키텍처를 지원 하는지 확인 하세요.

<a name="MT0015" />

### <a name="mt0015-invalid-abi--supported-abis-are-i386-x8664--armv7-armv7llvm-armv7llvmthumb2-armv7s-armv7sllvm-armv7sllvmthumb2-arm64-and-arm64llvm"></a>MT0015: 잘못 된 ABI: *. 지원 되는 Abi는: i386, x86_64, armv7, armv7 + llvm, armv7 + llvm + thumb2, armv7s, armv7s + llvm, armv7s + llvm + thumb2, arm64 및 arm64 + llvm 합니다.

잘못 된 ABI mtouch에 전달 되었습니다. 유효한 ABI를 지정 하십시오.

<a name="MT0016" />

### <a name="mt0016-the-option--has-been-deprecated"></a>MT0016: 옵션 * 사용 되지 않습니다.

언급 한 mtouch 옵션이 사용 되지 않으며 무시 됩니다.

<a name="MT0017" />

### <a name="mt0017-you-should-provide-a-root-assembly"></a>MT0017: 루트 어셈블리를 제공 해야 합니다.

루트 어셈블리 (일반적으로 주 실행 파일)를 지정 하는 일을 해야 하는 앱을 빌드하는 경우.

<a name="MT0018" />

### <a name="mt0018-unknown-command-line-argument-"></a>MT0018: 알 수 없는 명령줄 인수: *.

Mtouch는 오류 메시지에 언급 된 명령줄 인수를 인식 하지 못합니다.

<a name="MT0019" />

### <a name="mt0019-only-one---loginstallkilllaunchdev-or---launchdebugsim-option-can-be-used"></a>MT0019: 하나만-[로그 | 설치 | 종료 | 시작] 개발 또는--[시작 | 디버그] sim 옵션을 사용할 수 있습니다.

가지 동시에 사용할 수 없는 mtouch에 대 한 몇 가지 옵션이 있습니다.

-  --logdev
-  --installdev
-  -killdev
-  -launchdev
-  -launchdebug
-  -launchsim

<a name="MT0020" />

### <a name="mt0020-the-valid-options-for--are-"></a>MT0020:에 대 한 유효한 옵션 '\*'는'\*'.

<a name="MT0021" />

### <a name="mt0021-cannot-compile-using-gccg---use-gcc-when-using-the-static-registrar-this-is-the-default-when-compiling-for-device-either-remove-the---use-gcc-flag-or-use-the-dynamic-registrar---registrardynamic"></a>MT0021: gcc를 사용 하 여 컴파일할 수 없습니다 / g + + (-사용 하 여 gcc) 정적 등록자 (이 경우 기본 장치에 대 한 컴파일)를 사용 하는 경우. 제거 하거나--사용 하 여 gcc 플래그 또는 동적 등록 기관을 사용 하 여 (-등록자: 동적).

<a name="MT0022" />

### <a name="mt0022-the-options---unsupported--enable-generics-in-registrar-and---registrar-are-not-compatible"></a>MT0022: 옵션 '-지원 되지 않는-enable-제네릭-에-등록 기관은 ' 및 '-등록자 ' 호환 되지 않습니다.

두 옵션을 제거 `--unsupported--enable-generics-in-registrar` 고 `--registrar`입니다. 제네릭 지원 기본 등록 기관은 7.2.1 Xamarin.iOS를 사용 하 여 시작 합니다.

이 오류가 더 이상 표시 됩니다 (명령줄 인수 `--unsupported--enable-generics-in-registrar` mtouch에서 제거 되었습니다).

<a name="MT0023" />

### <a name="mt0023-application-name-exe-conflicts-with-another-user-assembly"></a>MT0023: 응용 프로그램 이름 ' *.exe ' 다른 사용자 어셈블리와 충돌 합니다.

실행 가능한 어셈블리의 이름과 응용 프로그램의 앱에서 모든 dll 이름과 일치할 수 없습니다. 실행 파일의 이름을 수정 하십시오.

<a name="MT0024" />

### <a name="mt0024-could-not-find-required-file-"></a>MT0024: 필요한 파일을 찾을 수 없습니다 ' *'.

<a name="MT0025" />

### <a name="mt0025-no-sdk-version-was-provided-please-add---sdkxy-to-specify-which-ios-sdk-should-be-used-to-build-your-application"></a>MT0025: SDK 버전이 제공 되었습니다. 추가 하십시오 `--sdk=X.Y` 는 iOS를 지정 하려면 응용 프로그램을 빌드할 SDK를 사용 합니다.

<a name="MT0026" />

### <a name="mt0026-could-not-parse-the-command-line-argument--"></a>MT0026: 명령줄 인수 구문 분석 하지 못했습니다 ' *': *

<a name="MT0027" />

### <a name="mt0027-the-options--and--are-not-compatible"></a>MT0027: 옵션\*'및'\*' 호환 되지 않습니다.

<a name="MT0028" />

### <a name="mt0028-cannot-enable-pie--pie-when-targeting-ios-41-or-earlier-please-disable-pie--piefalse-or-set-the-deployment-target-to-at-least-ios-42"></a>MT0028: 원형을 사용할 수 없습니다 (-원형) 4.1 또는 그 이전 버전의 iOS를 대상으로 합니다. 원형을 해제 하십시오 (-원형: false) 이상 배포 대상으로 설정 하거나 iOS 4.2

<a name="MT0029" />

### <a name="mt0029-repl---enable-repl-is-only-supported-in-the-simulator---sim"></a>MT0029: REPL (-enable repl) 시뮬레이터 에서만 지원 됩니다 (-sim).

REPL은 시뮬레이터에 대 한 작성 하는 경우에 지원 됩니다. 즉, 전달 하는 경우 `--enable-repl` mtouch를를 전달 해야 `--sim`합니다.

<a name="MT0030" />

### <a name="mt0030-the-executable-name--and-the-app-name--are-different-this-may-prevent-crash-logs-from-getting-symbolicated-properly"></a>MT0030: 실행 파일 이름 (\*) 및 앱 이름 (\*) 다른 경우이 가져오기 기호화 된 제대로에서 크래시 로그를 하지 못할 수 있습니다.

Xcode symbolicates 하는 경우 (함수 이름 및 파일/줄 번호에 메모리 주소 변환) 프로세스 실행 파일 및 앱 이름이 다른 (확장명 없음) 하는 경우 실패할 수 있습니다.

문제를 해결 하려면 프로젝트의 빌드/iOS 응용 프로그램 옵션 또는 프로젝트의 빌드/출력 옵션에서 ' 어셈블리 이름 ' 변경 ' 응용 프로그램 이름 ' 변경이 중 하나입니다.

<a name="MT0031" />

### <a name="mt0031-the-command-line-arguments---enable-background-fetch-and---launch-for-background-fetch-require---launchsim-too"></a>MT0031: 명령줄 인수를 '-사용 백그라운드 페치 ' 및 '-시작에 대 한 백그라운드 페치 ' 필요 '-launchsim' 너무 합니다.

<a name="MT0032" />

### <a name="mt0032-the-option---debugtrack-is-ignored-unless---debug-is-also-specified"></a>MT0032: 옵션 '-debugtrack'은 무시 '-디버그 '도 지정 합니다.

<a name="MT0033" />

### <a name="mt0033-a-xamarinios-project-must-reference-either-monotouchdll-or-xamariniosdll"></a>MT0033: monotouch.dll 또는 Xamarin.iOS.dll Xamarin.iOS 프로젝트를 참조 해야 합니다.

<a name="MT0034" />

### <a name="mt0034-cannot-include-both-monotouchdll-and-xamariniosdll-in-the-same-xamarinios-project----is-referenced-explicitly-while--is-referenced-by-"></a>MT0034:-동일한 Xamarin.iOS 프로젝트에서 'monotouch.dll' 및 'Xamarin.iOS.dll'를 포함할 수 없습니다 '\*'은 명시적으로 참조 하는 동안 '\*'에서 참조 하는 ' *'.

<!-- MT0035 unused -->

<a name="MT0036" />

### <a name="mt0036-cannot-launch-a--simulator-for-a--app-please-enable-the-correct-architectures-in-your-projects-ios-build-options-advanced-page"></a>MT0036: 시작할 수 없습니다는 *에 대 한 시뮬레이터를 * 앱. 프로젝트의 iOS 빌드 옵션 (고급 페이지)에서 올바른 architecture(s) 사용 하도록 설정 하세요.

<a name="MT0037" />

### <a name="mt0037-monotouchdll-is-not-64-bit-compatible-either-reference-xamariniosdll-or-do-not-build-for-a-64-bit-architecture-arm64-andor-x8664"></a>MT0037: monotouch.dll 하지 64 비트와 호환 됩니다. Xamarin.iOS.dll, 참조 또는 64 비트 아키텍처 (ARM64 및/또는 x86_64)를 작성 하지 마십시오.

<a name="MT0038" />

### <a name="mt0038-the-old-registrars---registraroldstaticolddynamic-are-not-supported-when-referencing-xamariniosdll"></a>MT0038: 이전 등록자 (-등록자: oldstatic | olddynamic) Xamarin.iOS.dll 참조 하는 경우 지원 되지 않습니다.

<a name="MT0039" />

### <a name="mt0039-applications-targeting-armv6-cannot-reference-xamariniosdll"></a>MT0039: ARMv6를 대상으로 하는 응용 프로그램 Xamarin.iOS.dll 참조할 수 없습니다.

<a name="MT0040" />

### <a name="mt0040-could-not-find-the-assembly--referenced-by-"></a>MT0040: 어셈블리를 찾을 수 없습니다 '\*', 참조 하 여'\*'.

<a name="MT0041" />

### <a name="mt0041-cannot-reference-both-monotouchdll-and-xamariniosdll"></a>'Monotouch.dll' 및 'Xamarin.iOS.dll' MT0041: 참조할 수 없습니다.

<a name="MT0042" />

### <a name="mt0042-no-reference-to-either-monotouchdll-or-xamariniosdll-was-found-a-reference-to-monotouchdll-will-be-added"></a>MT0042: monotouch.dll 또는 Xamarin.iOS.dll 참조가 없는 찾을 수 있습니다. Monotouch.dll에 대 한 참조가 추가 됩니다.

<a name="MT0043" />

### <a name="mt0043-the-boehm-garbage-collector-is-currently-not-supported-when-referencing-xamariniosdll-the-sgen-garbage-collector-has-been-selected-instead"></a>MT0043: Boehm 가비지 수집기는 현재 지원 되지 않습니다 'Xamarin.iOS.dll'를 참조 하는 경우. SGen 가비지 수집기가 대신 선정 되었습니다.

SGen 가비지 수집기는 통합 프로젝트를 사용 하 여 지원 됩니다. Boehm 가비지 수집기로 지정 하는 추가 mtouch 플래그가 없으므로 있는지 확인 하십시오.

<a name="MT0044" />

### <a name="mt0044---listsim-is-only-supported-with-xcode-60-or-later"></a>MT0044:-listsim 에서만 지원 됩니다 Xcode 6.0 이상.

최신 Xcode 버전을 설치 합니다.

<a name="MT0045" />

### <a name="mt0045---extension-is-only-supported-when-using-the-ios-80-or-later-sdk"></a>MT0045:-iOS를 사용 하는 경우에 확장 사용할 SDK 8.0 (이상).

<!-- MT0046 is not reported anymore -->

<a name="MT0047" />

### <a name="mt0047-the-minimum-deployment-target-for-unified-applications-is-511-the-current-deployment-target-is--please-select-a-newer-deployment-target-in-your-projects-ios-application-options"></a>MT0047: 최소 배포 통합 응용 프로그램에 대 한 대상이 5.1.1, 현재 배포 대상은 ' *'. 프로젝트의 iOS 응용 프로그램 옵션의에서 최신 배포 대상을 선택 하세요.

<!-- MT0048 is not reported anymore -->

<a name="MT0049" />

### <a name="mt0049-framework-is-supported-only-if-deployment-target-is-80-or-later--features-might-not-work-correctly"></a>MT0049: *.framework 배포 대상이 8.0 이상 하는 경우에 지원 됩니다. * 기능이 제대로 작동 하지 않을 수 있습니다.

지정된 된 프레임 워크 배포 대상을 참조 하는 iOS 버전에서 지원 되지 않습니다. 배포 대상 최신 iOS 버전으로 업데이트 하거나 앱에서 지정된 된 프레임 워크의 사용을 제거 합니다.

<!-- MT0050 is not reported anymore -->

<a name="MT0051" />

### <a name="mt0051-xamarinios--requires-xcode-50-or-later-the-current-xcode-version-found-in--is-"></a>MT0051: Xamarin.iOS * Xcode 5.0 이상이 필요 합니다. 현재 Xcode 버전 (있는 *)는 *입니다.

최신 Xcode를 설치 합니다.

<a name="MT0052" />

### <a name="mt0052-no-command-specified"></a>MT0052: 명령을 지정 합니다.

Mtouch에 대 한 지정 된 동작이 없습니다.

<!-- 0053 is used by mmp -->

<a name="MT0054" />

### <a name="mt0054-unable-to-canonicalize-the-path--"></a>MT0054: 경로 정형화할 수 없습니다. ' *': *

내부 오류입니다. 이 오류를 표시 하는 경우 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT0055" />

### <a name="mt0055-the-xcode-path--does-not-exist"></a>MT0055: Xcode 경로 ' *'가 없습니다.

Xcode 경로 사용 하 여 전달 `--sdkroot` 존재 하지 않습니다. 올바른 경로 지정 하십시오.

<a name="MT0056" />

### <a name="mt0056-cannot-find-xcode-in-the-default-location-applicationsxcodeapp-please-install-xcode-or-pass-a-custom-path-using---sdkroot-path"></a>MT0056: 기본 위치에서 Xcode를 찾을 수 없습니다 (/ Applications/Xcode.app). --Sdkroot를 사용 하 여 사용자 지정 경로 전달 하거나 Xcode를 설치 하십시오 <path>합니다.

<a name="MT0057" />

### <a name="mt0057-cannot-determine-the-path-to-xcodeapp-from-the-sdk-root--please-specify-the-full-path-to-the-xcodeapp-bundle"></a>MT0057: sdk 루트에서 Xcode.app 경로 확인할 수 없습니다. ' *'. Xcode.app 번들의 전체 경로 지정 하십시오.

전달 되는 경로 사용 하 여 `--sdkroot` 유효한 Xcode 앱을 지정 하지 않습니다. Xcode 앱에 대 한 경로 지정 하십시오.

<a name="MT0058" />

### <a name="mt0058-the-xcodeapp--is-invalid-the-file--does-not-exist"></a>MT0058: Xcode.app '\*' 잘못 되었습니다 (파일 '\*' 존재 하지 않습니다).

전달 되는 경로 사용 하 여 `--sdkroot` 유효한 Xcode 앱을 지정 하지 않습니다. Xcode 앱에 대 한 경로 지정 하십시오.

<a name="MT0059" />

### <a name="mt0059-could-not-find-the-currently-selected-xcode-on-the-system-"></a>MT0059: 시스템에서 현재 선택한 Xcode를 찾을 수 없습니다. *

<a name="MT0060" />

### <a name="mt0060-could-not-find-the-currently-selected-xcode-on-the-system-xcode-select---print-path-returned--but-that-directory-does-not-exist"></a>MT0060: 시스템에서 현재 선택한 Xcode를 찾을 수 없습니다. ' xcode-select--인쇄-path' 반환 ' *'는 하지만, 디렉터리가 존재 하지 않습니다.

<a name="MT0061" />

### <a name="mt0061-no-xcodeapp-specified-using---sdkroot-using-the-system-xcode-as-reported-by-xcode-select---print-path-"></a>MT0061: Xcode.app specified (사용--sdkroot), ' xcode-select--인쇄 경로 '가 보고 시스템 Xcode를 사용 하 여: *

이 Xcode 될를 설명 하는 정보 제공 용 이므로 경고를 사용 하므로 아무 것도 지정 합니다.

<a name="MT0062" />

### <a name="mt0062-no-xcodeapp-specified-using---sdkroot-or-xcode-select---print-path-using-the-default-xcode-instead-"></a>MT0062: Xcode.app specified (--sdkroot 또는 ' xcode-select--인쇄-path' 사용), Xcode 기본값 대신 사용 합니다. *

이 Xcode 될를 설명 하는 정보 제공 용 이므로 경고를 사용 하므로 아무 것도 지정 합니다.

<a name="MT0063" />

### <a name="mt0063-cannot-find-the-executable-in-the-extension--no-cfbundleexecutable-entry-in-its-infoplist"></a>MT0063: 확장에서 실행 파일을 찾을 수 없습니다 * (해당 Info.plist에서 CFBundleExecutable 항목 없음)

하지만 항목을 빌드하는 동안 자동으로 생성 해야 모든 Info.plist (CFBundleExecutable 항목 사용)는 실행 파일을 있어야 합니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0064" />

### <a name="mt0064-xamarinios-only-supports-embedded-frameworks-with-unified-projects"></a>MT0064: Xamarin.iOS 통합 프로젝트를 사용 하 여 포함 된 프레임 워크만 지원합니다.

Xamarin.iOS는만 포함 된 프레임 워크를 지원 통합 API를 사용 하는 경우 통합 API를 사용 하도록 프로젝트를 업데이트 하세요.

<a name="MT0065" />

### <a name="mt0065-xamarinios-only-supports-embedded-frameworks-when-deployment-target-is-at-least-80-current-deployment-target--embedded-frameworks-"></a>MT0065: Xamarin.iOS 경우에 지원 포함 된 프레임 워크 배포 대상이 8.0 이상 (현재 배포 대상은: * 프레임 워크를 포함 합니다. *)

Xamarin.iOS 배포 대상 이므로 8.0 이상 (이전 버전 iOS에서는 포함 된 프레임 워크를 지원 하지 않음) 하는 경우에 포함 된 프레임 워크를 지원 합니다.

8.0 이상으로 배포 대상이 프로젝트 Info.plist 업데이트 하십시오.

<a name="MT0066" />

### <a name="mt0066-invalid-build-registrar-assembly-"></a>MT0066: 잘못 된 빌드 등록자 어셈블리: *

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0067" />

### <a name="mt0067-invalid-registrar-"></a>MT0067: 잘못 된 등록 기관: *

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0068" />

### <a name="mt0068-invalid-value-for-target-framework-"></a>MT0068: 대상 프레임 워크에 대 한 값이 잘못 되었습니다: *.

잘못 된 대상 프레임 워크를 사용 하 여 전달 된--대상 프레임 워크 인수입니다. 올바른 대상 프레임 워크를 지정 하십시오.

<a name="MT0069" />

<!--### MT0069: currently unused -->

<a name="MT0070" />

### <a name="mt0070-invalid-target-framework--valid-target-frameworks-are-"></a>MT0070: 잘못 된 대상 프레임 워크: *. 올바른 대상 프레임 워크는: *.

잘못 된 대상 프레임 워크를 사용 하 여 전달 된--대상 프레임 워크 인수입니다. 올바른 대상 프레임 워크를 지정 하십시오.

<a name="MT0071" />

### <a name="mt0071-unknown-platform--this-usually-indicates-a-bug-in-xamarinios-please-file-a-bug-report-at-httpbugzillaxamarincom-with-a-test-case"></a>MT0071: 알 수 없는 플랫폼: *. 일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com 테스트 사례를 사용 하 여 합니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0072" />

### <a name="mt0072-extensions-are-not-supported-for-the-platform-"></a>MT0072: 플랫폼에 대 한 확장이 지원 되지 않습니다 ' *'.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0073" />

### <a name="mt0073-xamarinios--does-not-support-a-deployment-target-of--the-minimum-is--please-select-a-newer-deployment-target-in-your-projects-infoplist"></a>MT0073: Xamarin.iOS *의 배포 대상을 지원 하지 않습니다 * (최소값은 *). 프로젝트의 Info.plist에 최신 배포 대상을 선택 하세요.

최소 배포 대상이; 오류 메시지에 지정 된 프로젝트 Info.plist의 최신 배포 대상을 선택 하세요.

배포 대상 업데이트 가능 하지 않은 경우 다음 사용 하십시오는 이전 버전의 Xamarin.iOS.

<a name="MT0074" />

### <a name="mt0074-xamarinios--does-not-support-a-minimum-deployment-target-of--the-maximum-is--please-select-an-older-deployment-target-in-your-projects-infoplist-or-upgrade-to-a-newer-version-of-xamarinios"></a>MT0074: Xamarin.iOS *의 최소 배포 대상을 지원 하지 않습니다 * (최대값은 *). 프로젝트의 Info.plist에 이전 배포 대상을 선택 하거나 최신 버전의 Xamarin.iOS 업그레이드 하세요.

Xamarin.iOS 최소 배포 대상에 대 한이 특정 버전의 Xamarin.iOS 빌드된 버전 보다 높은 버전을 설정 하는 것을 지원 하지 않습니다.

프로젝트 Info.plist의 이전 최소 배포 대상을 선택 하거나 최신 버전의 Xamarin.iOS 업그레이드 하세요.

<a name="MT0075" />

### <a name="mt0075-invalid-architecture--for--projects-valid-architectures-are-"></a>MT0075: 잘못 된 아키텍처 ' *'에 대 한 * 프로젝트입니다. 올바른 아키텍처는: *

잘못 된 아키텍처를 지정 했습니다. 아키텍처가 유효한 지 확인 하세요.

<a name="MT0076" />

### <a name="mt0075-no-architecture-specified-using-the---abi-argument-an-architecture-is-required-for--projects"></a>MT0075: 아키텍처 (-abi 인수를 사용 하 여) 지정 합니다. 아키텍처에 대 한 필요 * 프로젝트입니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0077" />

### <a name="mt0076-watchos-projects-must-be-extensions"></a>WatchOS 프로젝트 MT0076: 확장 해야 합니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0078" />

### <a name="mt0077-incremental-builds-are-enabled-with-a-deployment-target--80-currently--this-is-not-supported-the-resulting-application-will-not-launch-on-ios-9-so-the-deployment-target-will-be-set-to-80"></a>MT0077: 증분 빌드를 배포 대상 < 8.0을 사용 하 여 활성화 됩니다 (현재 *). 지원 되지 않습니다 (응용 프로그램에서 iOS 9는 시작 되지 않는), 배포 대상 8.0으로 설정 됩니다.

이 배포 대상을 증분 빌드가 작업 제대로 8.0이이 빌드에 대 한로 설정 된에 알리는 경고입니다.

증분 빌드는 배포 대상 이므로 8.0 이상 (그렇지 않은 경우 iOS 9에서 완성 된 응용 프로그램 시작 되지 않는) 하는 경우에 지원 됩니다.

<a name="MT0079" />

### <a name="mt0078-the-recommended-xcode-version-for-xamarinios--is-xcode--or-later-the-current-xcode-version-found-in--is-"></a>MT0078: 권장 되는 Xcode 버전 Xamarin.iOS에 대 한 * Xcode가 * 이상. 현재 Xcode 버전 (있는 *)는 *입니다.

현재 버전의 Xcode이이 버전의 Xamarin.iOS에 대 한 권장 되는 버전의 Xcode 아닙니다 알리는 경고입니다.

최적의 동작 보장 하기 위해 Xcode를 업그레이드 하세요.

<a name="MT0080" />

### <a name="mt0080-disabling-newrefcount---new-refcountfalse-is-deprecated"></a>MT0080: NewRefCount 사용 하지 않도록 설정,--새로 만들기-refcount:false, 사용 되지 않습니다.

이 되었음을 알리는 경고 요청을 사용 하지 않도록 새 refcount (-새로 만들기-refcount:false) 무시 되었습니다.

새 refcount 기능은 이제 모든 프로젝트에 대 한 필수 및 불가능 하므로 더 이상 사용 하지 않도록 설정 합니다.

<a name="MT0081" />

### <a name="mt0081-the-command-line-argument---download-crash-report-also-requires---download-crash-report-to"></a>MT0081: 명령줄 인수-다운로드 충돌 보고서도-다운로드-충돌-보고서-하 필요합니다.

<a name="MT0082" />

### <a name="mt0082-repl---enable-repl-is-only-supported-when-linking-is-not-used---nolink"></a>MT0082: REPL (-repl 사용) 연결 사용 되지 않는 경우에 지원 됩니다 (-nolink).

<a name="MT0083" />

### <a name="mt0083-asm-only-bitcode-is-not-supported-on-watchos-use-either---bitcodemarker-or---bitcodefull"></a>MT0083: Asm 전용 bitcode watchOS에서 지원 되지 않습니다. 두-bitcode 사용: 표식 또는-bitcode: 전체.

<a name="MT0084" />

### <a name="mt0084-bitcode-is-not-supported-in-the-simulator-do-not-pass---bitcode-when-building-for-the-simulator"></a>MT0084: Bitcode는 시뮬레이터에서 지원 되지 않습니다. 시뮬레이터를 빌드할 때에-bitcode를 전달 하지 마십시오.

<a name="MT0085" />

### <a name="mt0085-no-reference-to--was-found-it-will-be-added-automatically"></a>MT0085: 없음에 대 한 참조 ' *'를 찾을 수 있습니다. 자동으로 추가 됩니다.

<a name="MT0086" />

### <a name="mt0086-a-target-framework---target-framework-must-be-specified-when-building-for-tvos-or-watchos"></a>MT0086: 대상 프레임 워크 (-대상 프레임 워크) TVOS WatchOS에 구축 하는 경우 지정 해야 합니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0087" />

### <a name="mt0087-incremental-builds---fastdev-is-not-supported-with-the-boehm-gc-incremental-builds-will-be-disabled"></a>MT0087: 증분 빌드 (-fastdev) Boehm GC를 사용 하 여 지원 되지 않습니다. 증분 빌드를 사용할 수 없습니다.

<a name="MT0088" />

### <a name="mt0088-the-gc-must-be-in-cooperative-mode-for-watchos-apps-please-remove-the---coopfalse-argument-to-mtouch"></a>MT0088: GC는 watchOS 앱에 대해 공동 작업 모드에 있어야 합니다. 제거 하십시오 mtouch-coop: false 인수입니다.

<a name="MT0089" />

### <a name="mt0089-the-option--cannot-take-the-value--when-cooperative-mode-is-enabled-for-the-gc"></a>MT0089: 옵션 '\*'값을 가져올 수 없습니다'\*' GC에 대 한 공동 작업 모드를 사용 하는 경우.

<a name="MT0091" />

### <a name="mt0091-this-version-of-xamarinios-requires-the--sdk-shipped-with-xcode--either-upgrade-xcode-to-get-the-required-header-files-or-set-the-managed-linker-behaviour-to-link-framework-sdks-only-to-try-to-avoid-the-new-apis"></a>MT0091:이 버전의 Xamarin.iOS에는 * SDK (Xcode와 함께 제공 *). 필요한 헤더 파일을 가져오거나 링크 프레임 워크 Sdk 전용 (하려고 새 api)로 관리 되는 링커 동작을 설정 하는 Xcode를 업그레이드 하는 중입니다.

Xamarin.iOS 응용 프로그램을 빌드하는 오류 메시지에서 지정 된 SDK 버전에서 헤더 파일에 필요 합니다. 이 오류를 수정 하는 권장된 방법은 필요한 SDK 받기 위해 Xcode를 업그레이드 하는 것, 여기에 모든 필수 헤더 파일이 포함 됩니다. 여러 버전의 Xcode 설치 했거나 기본이 아닌 위치에는 Xcode를 사용 하려는 경우에 IDE의 기본 설정에서 올바른 Xcode 위치를 설정 해야 합니다.

잠재적인 대체 솔루션으로 관리 되는 링커를 사용 하도록 설정 합니다. 사용 되지 않는 API 등 대부분의 경우, 누락 된 (또는 불완전) 헤더 파일이 있는 새 API 제거 합니다. 그러나가 제공이 프로젝트에 Xcode 1 보다 최신 SDK에 도입 된 API를 사용 하는 경우를 작동 하지 않습니다.

몰 랐 하 어 요 솔루션을 이전 버전의 Xamarin.iOS 사용 하는 것을 프로젝트에 SDK를 지 원하는 하나 필요 합니다.

<!-- MT0092 used by mlaunch -->

<a name="MT0093" />

### <a name="mt0093-could-not-find-mlaunch"></a>MT0093: 'mlaunch'를 찾을 수 없습니다.

<!-- MT0094 is not reported anymore -->

<a name="MT0095" />

### <a name="mt0095-aot-files-could-not-be-copied-to-the-destination-directory-dest-error"></a>MT0095: Aot 파일 {dest} 대상 디렉터리로 복사할 수 없습니다. {error}

<a name="MT0096" />

### <a name="mt0096-no-reference-to-xamariniosdll-was-found"></a>MT0096: Xamarin.iOS.dll에 참조가 없는 찾을 수 있습니다.

<!-- MT0097: used by mmp -->
<!-- MT0098: used by mmp -->

<a name="MT0099" />

### <a name="mt0099-internal-error--please-file-a-bug-report-with-a-test-case-httpbugzillaxamarincom"></a>MT0099: 내부 오류 *. 테스트 사례를 사용 하 여 버그 보고서를 제출 하세요 (http://bugzilla.xamarin.com)합니다.

Xamarin.iOS에는 내부 일관성 검사가 실패 하면이 오류 메시지가 보고 됩니다.

Xamarin.iOS;에 버그가이 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0100" />

### <a name="mt0100-invalid-assembly-build-target--please-file-a-bug-report-with-a-test-case-httpbugzillaxamarincom"></a>MT0100: 잘못 된 어셈블리 빌드 대상: ' *'. 테스트 사례를 사용 하 여 버그 보고서를 제출 하세요 (http://bugzilla.xamarin.com)합니다.

Xamarin.iOS에는 내부 일관성 검사가 실패 하면이 오류 메시지가 보고 됩니다.

이 값은 항상 Xamarin.iOS;의 버그 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 사례를 사용 하 여 합니다.

<a name="MT0101" />

### <a name="mt0101-the-assembly--is-specified-multiple-times-in---assembly-build-target-arguments"></a>MT0101: 어셈블리 ' *'-어셈블리 빌드 대상을 인수에 여러 번 지정 되었습니다.

오류 메시지에 언급 된 어셈블리에는-어셈블리 빌드 대상을 인수에 여러 번 지정 되었습니다. 각 어셈블리는 한 번 언급만 있는지 확인 하십시오.

<a name="MT0102" />

### <a name="mt0102-the-assemblies--and--have-the-same-target-name--but-different-targets--and-"></a>MT0102: 어셈블리\*'및'\*' 대상 이름이 같은 ('\*'), 다른 대상 ('\*' 및 ' *').

오류 메시지에 언급 된 어셈블리를 빌드 대상을 충돌 하는 경우

예를 들어:

    --assembly-build-target:Assembly1.dll=framework=MyBinary --assembly-build-target:Assembly2.dll=dynamiclibrary=MyBinary

이 예제에서는 동일한 브랜드를 사용 하 여 동적 라이브러리와 프레임 워크를 만들 하려고 합니다. (`MyBinary`).

<a name="MT0103" />

### <a name="mt0103-the-static-object--contains-more-than-one-assembly--but-each-static-object-must-correspond-with-exactly-one-assembly"></a>MT0103: 정적 개체 '\*' 둘 이상의 어셈블리가 포함 된 ('\*'), 되지만 각 정적 개체는 정확히 하나의 어셈블리와 일치 해야 합니다.

오류 메시지에 언급 된 어셈블리는 모두 단일 정적 개체가 컴파일됩니다. 이 허용 되지, 다른 정적 개체에 모든 어셈블리를 컴파일해야 합니다.

예를 들어:

    --assembly-build-target:Assembly1.dll=staticobject=MyBinary --assembly-build-target:Assembly2.dll=staticobject=MyBinary

이 예제에서는 정적 개체를 작성 하려고 합니다. (`MyBinary`) 두 어셈블리 구성 (`Assembly1.dll` 및 `Assembly2.dll`)에 허용 되지 않습니다.

<a name="MT0105" />

### <a name="mt0105-no-assembly-build-target-was-specified-for-"></a>MT0105: 어셈블리 빌드 대상이 없습니다에 대해 지정 된 ' *'.

사용 하 여 대상 빌드 어셈블리를 지정 하 `--assembly-build-target`, 앱에서 모든 어셈블리 할당 빌드 대상에 있어야 합니다.

이 오류는 오류 메시지에 언급 된 어셈블리에 할당 하는 대상 빌드 어셈블리 없을 때 보고 됩니다.

에 대 한 설명서를 참조 하세요. `--assembly-build-target` 대 한 자세한 내용은 합니다.

<a name="MT0106" />

### <a name="mt0106-the-assembly-build-target-name--is-invalid-the-character--is-not-allowed"></a>MT0106: 어셈블리 빌드 대상 이름 '\*' 올바르지 않습니다: 문자 '\*' 허용 되지 않습니다.

어셈블리 빌드 대상 이름에는 유효한 파일 이름 이어야 합니다.

예를 들어 이러한 값이이 오류가 트리거됩니다.

    --assembly-build-target:Assembly1.dll=staticobject=my/path.o

때문에 `my/path.o` 디렉터리 구분 문자로 인해 유효한 파일 이름이 아닙니다.

<a name="MT0107" />

### <a name="mt0107-the-assemblies--have-different-custom-llvm-optimizations--which-is-not-allowed-when-they-are-all-compiled-to-a-single-binary"></a>MT0107: 어셈블리\*' 다른 사용자 지정 LLVM 최적화 (\*)에 모두 단일 바이너리를 컴파일할 때 허용 되지 않습니다.

<a name="MT0108" />

### <a name="mt0108-the-assembly-build-target--did-not-match-any-assemblies"></a>MT0108: 어셈블리 빌드 대상 ' *'는 모든 어셈블리와 일치 하지 않습니다.

<a name="MT0109" />

### <a name="mt0109-the-assembly-0-was-loaded-from-a-different-path-than-the-provided-path-provided-path-1-actual-path-2"></a>MT0109: 어셈블리 '{0}' 제공된 된 경로 다른 경로에서 로드 된 (경로 제공 합니다. {1}, 실제 경로: {2}).

이 응용 프로그램에서 참조 하는 어셈블리 요청 된 수보다 다른 위치에서 로드 되었음을 나타내는 경고입니다.

앱 이름이 같은 있지만 (첫 번째 어셈블리에만 사용) 하는 예기치 않은 결과가 발생할 수 있는 다양 한 위치에서 여러 어셈블리를 참조 하 고 있다는 것일 수 있습니다.

<a name="MT0110" />

### <a name="mt0110-incremental-builds-have-been-disabled-because-this-version-of-xamarinios-does-not-support-incremental-builds-in-projects-that-include-third-party-binding-libraries-and-that-compiles-to-bitcode"></a>MT0110:이 버전의 Xamarin.iOS 타사 바인딩 라이브러리를 포함 하 고 bitcode 컴파일되는 프로젝트의 증분 빌드를 지원 하지 않으므로 증분 빌드를 사용할 수 없습니다.

이 버전의 Xamarin.iOS 타사 바인딩 라이브러리를 포함 하 고 bitcode (tvOS 및 watchOS 프로젝트)로 컴파일되는 프로젝트의 증분 빌드를 지원 하지 않으므로 증분 빌드를 사용할 수 없습니다.

사용자의 조치가 필요,이 메시지는 정보로 합니다.

자세한 내용은 참조 하세요. 버그 #[51710](https://bugzilla.xamarin.com/show_bug.cgi?id=51710)합니다.

이 경고는 더 이상 보고 되지 않습니다.

<a name="MT0111" />

### <a name="mt0111-bitcode-has-been-enabled-because-this-version-of-xamarinios-does-not-support-building-watchos-projects-using-llvm-without-enabling-bitcode"></a>MT0111: Bitcode 사용 하도록 설정한이 버전의 Xamarin.iOS 빌드 watchOS를 지원 하지 않으므로 bitcode를 사용 하지 않고 LLVM을 사용 하는 프로젝트입니다.

Bitcode 사용 하도록 설정한 자동으로이 버전의 Xamarin.iOS 빌드 watchOS를 지원 하지 않으므로 bitcode를 사용 하지 않고 LLVM을 사용 하는 프로젝트입니다.

사용자의 조치가 필요,이 메시지는 정보로 합니다.

자세한 내용은 참조 하세요. 버그 #[51634](https://bugzilla.xamarin.com/show_bug.cgi?id=51634)합니다.

<a name="MT0112" />

### <a name="mt0112-native-code-sharing-has-been-disabled-because-"></a>MT0112: 네이티브 코드 공유 때문에 사용할 수 *

코드 공유를 사용할 수는 여러 가지가 있습니다.

* 컨테이너 앱의 배포 대상은 iOS 8.0 보다 이전 이므로 (있기 *)).

네이티브 코드 공유 필요 iOS 8.0 네이티브 코드 공유 사용자 프레임 워크를 사용 하 여 구현 되기 때문에 iOS 8.0에 도입 되었습니다.

* 컨테이너 앱 I18N 어셈블리 (*)를 포함 때문에 합니다.

네이티브 코드 공유 현재 지원 되지 않습니다 컨테이너 앱 I18N 어셈블리를 포함 하는 경우.

* 컨테이너 앱에 관리 되는 링커 (*)에 대 한 사용자 지정 xml 정의가 있으므로

관리 되는 링커에 대 한 사용자 지정 xml 정의 사용 하는 프로젝트에 대 한 지원 되지 않습니다 필요한 네이티브 코드를 공유 합니다.

<a name="MT0113" />

### <a name="mt0113-native-code-sharing-has-been-disabled-for-the-extension--because-"></a>MT0113: 네이티브 코드 공유 비활성화 된 확장에 대 한 ' *' 때문에 *.

* bitcode 옵션 컨테이너 앱 간에 서로 다르기 때문에 (\*) 및 확장 (\*).

  네이티브 코드 공유 bitcode 옵션은 코드를 공유 하는 프로젝트 간에 일치 해야 합니다.

* 때문에--어셈블리 빌드 대상이 옵션은 컨테이너 앱에 따라 다릅니다 (\*) 및 확장 (\*).

  네이티브 코드를 공유 하려면--어셈블리 빌드 대상이 옵션은 코드를 공유 하는 프로젝트 간에 동일 합니다.

  증분 빌드도 서로 겹치지 설정 또는 해제 되는 모든 프로젝트에서이 상태가 발생할 수 있습니다.

* 컨테이너 앱 간에 I18N 어셈블리 다르기 때문에 (\*) 및 확장 (\*).

  네이티브 코드 공유가 현재 지원 되지 않습니다 I18N 어셈블리를 포함 하는 확장에 대 한 합니다.

* AOT 컴파일러에 대 한 인수 컨테이너 앱 간에 다르기 때문에 (\*) 및 확장 (\*).

  공유 하는 네이티브 코드 AOT 컴파일러에 대 한 인수는 코드를 공유 하는 프로젝트 간에 다르지 않으면 필요 합니다.

* 다른 AOT 컴파일러 인수는 컨테이너 앱 간에 다르기 때문에 (\*) 및 확장 (\*).

  공유 하는 네이티브 코드 AOT 컴파일러에 대 한 인수는 코드를 공유 하는 프로젝트 간에 다르지 않으면 필요 합니다.

  이 상태는 ' 모든 32 비트 부동 연산으로 수행 64 비트 float' 프로젝트 간에 다를 경우에 발생 합니다.

* LLVM 사용 되거나 둘 다 컨테이너 앱에서 사용 하지 않도록 설정 되지 때문에 (\*) 및 확장 (\*).

  네이티브 코드 공유는 LLVM 사용 되거나 코드를 공유 하는 모든 프로젝트에 대해 사용 하지 않도록 설정 해야 합니다.

* 컨테이너 앱 간의 관리 되는 링커 설정이 다르기 때문에 (\*) 및 확장 (\*).

  네이티브 코드 공유는 관리 되는 링커 설정 코드를 공유 하는 모든 프로젝트에 대해 동일 해야 합니다.

* 관리 되는 링커에 대 한 작업을 건너뛰었습니다 어셈블리 컨테이너 앱 간에 다르기 때문에 (\*) 및 확장 (\*).

  네이티브 코드 공유는 관리 되는 링커 설정 코드를 공유 하는 모든 프로젝트에 대해 동일 해야 합니다.

* 확장 관리 되는 링커 (*)에 대 한 사용자 지정 xml 정의 있으므로

  관리 되는 링커에 대 한 사용자 지정 xml 정의 사용 하는 프로젝트에 대 한 지원 되지 않습니다 필요한 네이티브 코드를 공유 합니다.

* ABI에 대 한 컨테이너 앱 빌드하지 않는 때문에 * (하는 동안이 ABI에 대 한 확장을 빌드하고).

  네이티브 코드 공유 컨테이너 앱에 대 한 모든 앱 확장을 작성 하는 모든 아키텍처에 대 한 빌드는 필요 합니다.

  예를 들어:이 상태 ARM64 + ARMv7 용 확장 작성 하지만 ARM64 용 컨테이너 앱만 작성 하는 경우에 발생 합니다.

* ABI에 대 한 컨테이너 앱을 빌드하고 있으므로 \*, 확장의 ABI를 사용 하 여 호환 되지 않는 (\*).

  네이티브 코드 공유에 동일한 API에 대 한 모든 프로젝트를 빌드하는 필요 합니다.

  예를 들어:이 상태 ARMv7 + llvm thumb2에 대 한 확장 작성 하지만 컨테이너 앱만 ARMv7 + llvm 작성 하는 경우에 발생 합니다.

* 컨테이너 앱은 어셈블리를 참조 하기 때문에 '\*'에서'\*' 확장에서 다른 버전을 참조 하는 동안, ' *'.

  네이티브 코드 공유 코드를 공유 하는 모든 프로젝트는 모든 어셈블리에 대 한 동일한 버전을 사용 해야 합니다.

<!-- MT0114: used by mmp -->

<a name="MT0115" />

### <a name="mt0115-it-is-recommended-to-reference-dynamic-symbols-using-code---dynamic-symbol-modecode-when-bitcode-is-enabled"></a>MT0115: 코드를 사용 하 여 동적 기호를 참조할 것이 좋습니다 (-동적 기호 모드 = 코드) bitcode 사용 되는 경우.

Xamarin.iOS 프로젝트는 자주 참조 네이티브 기호 동적으로 즉, 네이티브 링커가 네이티브 연결 프로세스 중 이러한 네이티브 기호를 제거할 수는 네이티브 링커가 이러한 기호를 사용 하는 보이지 않는 때문에 합니다.

Xamarin.iOS에서 네이티브 링커가 이러한 기호를 그대로 유지 하도록 요청 하는 일반적으로 (사용 하 여는 `-u symbol` 링커 플래그) 때 네이티브 링커가 bitcode에 대 한 컴파일을 허용 하지 않습니다 하지만 `-u` 플래그입니다.

Xamarin.iOS에는 대체 솔루션을 구현 했습니다: 이러한 기호를 참조 하는 추가 네이티브 코드 생성을 따라서 이러한 기호를 사용 하는 네이티브 링커가 표시 됩니다. Bitcode를 컴파일할 때 자동으로 수행 됩니다.

하는 경우 `--dynamic-symbol-mode=linker` 솔루션을 사용할 수 및 Xamarin.iOS 전달 하려고 합니다.이 대체 mtouch에 전달 됩니다 `-u` 네이티브 링커가를 합니다. 이 네이티브 링커 오류가 발생할 가능성이 됩니다.

솔루션 제거 하는 것은 `--dynamic-symbol-mode=linker` 추가 mtouch 인수 프로젝트의 빌드 옵션에서에서 인수입니다.

<!-- 0116 - 0124: free to use -->

<a name="MT0116" />

### <a name="mt0116-invalid-architecture-arch-32-bit-architectures-are-not-supported-when-deployment-target-is-11-or-later-make-sure-the-project-does-not-build-for-a-32-bit-architecture"></a>MT0116: 잘못 된 아키텍처: {arch}. 배포 대상 11 이상인 경우에 32 비트 아키텍처 지원 되지 않습니다. 32 비트 아키텍처에 대 한 프로젝트를 빌드하지 않는 있는지 확인 합니다.

iOS 11에 32 비트 응용 프로그램에 대 한 지원이 없습니다 배포 대상은 iOS 11 이상 경우 32 비트 응용 프로그램 빌드에 지원 되지 않습니다.

Arm64를를 프로젝트의 iOS 빌드 옵션에서 대상 아키텍처를 변경 하거나 이전 iOS 버전으로 프로젝트의 Info.plist에서 배포 대상을 변경 합니다.

<a name="MT0117" />

### <a name="mt0117-cant-launch-a-32-bit-app-on-a-simulator-that-only-supports-64-bit"></a>MT0117: 시뮬레이터만 지 원하는 64 비트에서 32 비트 앱을 시작할 수 없습니다.

<a name="MT0118" />

### <a name="mt0118-aot-files-could-not-be-found-at-the-expected-directory-msymdir"></a>MT0118: 예상된 디렉터리 '{msymdir}'에 Aot 파일을 찾을 수 없습니다.

<!-- 0119 - 0123: free to use -->

<a name="MT0123" />

### <a name="mt0123-the-executable-assembly--does-not-reference-"></a>MT0123: 실행 가능한 어셈블리를 *를 참조 하지 않습니다 * 합니다.

플랫폼 어셈블리에 참조를 찾을 수 없습니다 (Xamarin.iOS.dll / Xamarin.TVOS.dll / Xamarin.WatchOS.dll)에서 실행 가능한 어셈블리.

일반적으로 이런 플랫폼 어셈블리에 이르기까지 사용 하 여 실행 가능한 프로젝트에서 코드가 없는 경우 예를 들어이 오류는 빈 Main 메서드 (및 다른 코드가 없어야) 표시 됩니다.

```csharp
class Program {
    void Main (string[] args)
    {
    }
}
```

플랫폼 어셈블리의 API를 사용 하 여 오류를 해결 합니다.

```csharp
class Program {
    void Main (string[] args)
    {
        System.Console.WriteLine (typeof (UIKit.UIWindow));
    }
}
```

<a name="MT0124" />

### <a name="mt0124-could-not-set-the-current-language-to-lang-according-to-langlang-exception"></a>MT0124: '{lang}'에 현재 언어를 설정할 수 없습니다 (언어에 따라 {LANG} =): {exception 예외로}

현재 언어 오류 메시지의 언어를 설정할 수 없음을 나타내는 경고입니다.

현재 언어 시스템 언어 기본값으로 설정 됩니다.

<a name="MT0125" />

### <a name="mt0125-the---assembly-build-target-command-line-argument-is-ignored-in-the-simulator"></a>MT0125:--어셈블리-빌드 대상을 시뮬레이터에서 명령줄 인수는 무시 됩니다.

조치가 필요 하지 않습니다,이 메시지는 정보로 합니다.

<a name="MT0126" />

### <a name="mt0126-incremental-builds-have-been-disabled-because-incremental-builds-are-not-supported-in-the-simulator"></a>MT0126: 증분 빌드 시뮬레이터에서 지원 되지 않으므로 증분 빌드를 사용할 수 없습니다.

조치가 필요 하지 않습니다,이 메시지는 정보로 합니다.

<a name="MT0127" />

### <a name="mt0127-incremental-builds-have-been-disabled-because-this-version-of-xamarinios-does-not-support-incremental-builds-in-projects-that-include-more-than-one-third-party-binding-libraries"></a>MT0127:이 버전의 Xamarin.iOS 둘 것 뿐만 아니라 타사 바인딩 라이브러리를 포함 하는 프로젝트의 증분 빌드를 지원 하지 않으므로 증분 빌드를 사용할 수 없습니다.

이 버전의 Xamarin.iOS 항상 프로젝트를 빌드하지 않습니다 여러 타사 바인딩 라이브러리를 사용 하 여 올바르게 때문에 증분 빌드를 자동으로 사용할 수 없습니다.

조치가 필요 하지 않습니다,이 메시지는 정보로 합니다.

자세한 내용은 참조 하세요. 버그 #[52727](https://bugzilla.xamarin.com/show_bug.cgi?id=52727)합니다.

<a name="MT0128" />

### <a name="mt0128-could-not-touch-the-file--"></a>MT0128: 파일에 미치지 못했습니다 ' *': *

파일 (부분 빌드 제대로 수행 되었는지 확인 하는 실행)을 터치 하는 오류가 발생 했습니다.

이 경고는 대개 무시; 문제 발생 시 버그 (https://bugzilla.xamarin.com] (https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)) 조사 됩니다.

## <a name="mt1xxx-project-related-error-messages"></a>MT1xxx: 프로젝트와 관련 된 오류 메시지

### <a name="mt10xx-installer--mtouch"></a>MT10xx: 설치 관리자 / mtouch

<!--
 MT1xxx file copy / symlinks (project related)
  MT10xx installer.cs / mtouch.cs
  -->

<a name="MT1001" />

### <a name="mt1001-could-not-find-an-application-at-the-specified-directory"></a>MT1001: 지정된 된 디렉터리에서 응용 프로그램을 찾을 수 없습니다.

<a name="MT1002" />

### <a name="mt1002-could-not-create-symlinks-files-were-copied"></a>MT1002: symlink를 만들 수 없습니다, 그리고 파일 복사

<a name="MT1003" />

### <a name="mt1003-could-not-kill-the-application--you-may-have-to-kill-the-application-manually"></a>MT1003: 응용 프로그램을 종료 하지 못했습니다 ' *'. 응용 프로그램을 수동으로 중지 해야 합니다.

<a name="MT1004" />

### <a name="mt1004-could-not-get-the-list-of-installed-applications"></a>MT1004: 설치 된 응용 프로그램 목록을 가져올 수 없습니다.

<a name="MT1005" />

### <a name="mt1005-could-not-kill-the-application--on-the-device----you-may-have-to-kill-the-application-manually"></a>MT1005: 응용 프로그램을 종료 하지 못했습니다 '\*'장치의'\*': *-응용 프로그램을 수동으로 중지 해야 할 수 있습니다.

<a name="MT1006" />

### <a name="mt1006-could-not-install-the-application--on-the-device--"></a>MT1006: 응용 프로그램을 설치할 수 없습니다 '\*'장치의'\*': *.

<a name="MT1007" />

### <a name="mt1007-failed-to-launch-the-application--on-the-device---you-can-still-launch-the-application-manually-by-tapping-on-it"></a>MT1007: 응용 프로그램을 시작 하지 못했습니다 '\*'장치의'\*': *. 여전히 응용 프로그램을 탭 하 여 수동으로 시작할 수 있습니다.

<a name="MT1008" />

### <a name="mt1008-failed-to-launch-the-simulator"></a>MT1008: 시뮬레이터를 시작 하지 못했습니다.

Mtouch 시뮬레이터를 시작 하지 못한 경우이 오류가 보고 됩니다.   이 발생할 수 있습니다 경우에 따라 실행 되는 부실 하거나 데드 시뮬레이터 프로세스가 이미 있기 때문입니다.

Unix 명령줄에서 발급 한 명령은 중단된 시뮬레이터 프로세스 수: 있습니다.

```bash
$ launchctl list|grep UIKitApplication|awk '{print $3}'|xargs launchctl remove
```

<a name="MT1009" />

### <a name="mt1009-could-not-copy-the-assembly--to--"></a>MT1009: 어셈블리를 복사할 수 없습니다. '\*'에'\*': *

특정 버전의 Xamarin.iOS의 알려진된 문제입니다.

이 할 경우 다음 해결 방법을 시도해 보세요.

```bash
sudo chmod 0644 /Library/Frameworks/Xamarin.iOS.framework/Versions/Current/lib/mono/*/*.mdb
```

그러나 최신 버전의 Xamarin.iOS에서이 문제가 해결 되었는지, 이후 하세요 파일에서 새 버그 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 전체 버전 정보 및 빌드 로그 출력 합니다.

<a name="MT1010" />

### <a name="mt1010-could-not-load-the-assembly--"></a>MT1010: 어셈블리를 로드할 수 없습니다 ' *': *

<a name="MT1011" />

### <a name="mt1011-could-not-add-missing-resource-file-"></a>MT1011: 누락 된 리소스 파일을 추가할 수 없습니다. ' *'

<a name="MT1012" />

### <a name="mt1012-failed-to-list-the-apps-on-the-device--"></a>MT1012: 장치에서 앱을 나열 하지 못했습니다 ' *': *

<a name="MT1013" />

### <a name="mt1013-dependency-tracking-error-no-files-to-compare-please-file-a-bug-report-at-httpbugzillaxamarincom-with-a-test-case"></a>MT1013: 종속성 오류 추적: 비교할 파일이 없습니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com 테스트 사례를 사용 하 여 합니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 테스트 caes를 사용 하 여 합니다.

<a name="MT1014" />

### <a name="mt1014-failed-to-re-use-cached-version-of--"></a>MT1014: 다시의 캐시 된 버전을 사용 하지 못했습니다 ' *': *.

<a name="MT1015" />

### <a name="mt1015-failed-to-create-the-executable--"></a>MT1015:를 실행 파일을 만들지 못했습니다 ' *': *

<a name="MT1015" />

### <a name="mt1015-failed-to-create-the-executable--"></a>MT1015:를 실행 파일을 만들지 못했습니다 ' *': *

<a name="MT1016" />

### <a name="mt1016-failed-to-create-the-notice-file-because-a-directory-already-exists-with-the-same-name"></a>MT1016: 이름이 같은 디렉터리가 이미 있기 때문에 NOTICE 파일을 만들지 못했습니다.

디렉터리를 제거 `NOTICE` 프로젝트에서.

<a name="MT1017" />

### <a name="mt1017-failed-to-create-the-notice-file-"></a>MT1017: NOTICE 파일을 만들지 못했습니다: *.

<a name="MT1018" />

### <a name="mt1018-your-application-failed-code-signing-checks-and-could-not-be-installed-on-the-device--check-your-certificates-provisioning-profiles-and-bundle-ids-probably-your-device-is-not-part-of-the-selected-provisioning-profile-error-0xe8008015"></a>MT1018: 응용 프로그램 코드 서명 검사에 실패 한 및 장치에 설치할 수 없습니다 ' *'. 인증서와 프로 비전 프로필을 확인 하 고 번들 id 키를 누릅니다. 아마도 장치의의 일부가 아닌 선택한 프로 비전 프로필 (오류: 0xe8008015).

<a name="MT1019" />

### <a name="mt1019-your-application-has-entitlements-not-supported-by-your-current-provisioning-profile-and-could-not-be-installed-on-the-device--please-check-the-ios-device-log-for-more-detailed-information-error-0xe8008016"></a>MT1019: 응용 프로그램에 현재 프로 비전 프로필에 지원 되지 않습니다 자격 있고 장치에 설치할 수 없습니다 ' *'. 자세한 내용은 iOS 장치 로그를 확인 하세요 (오류: 0xe8008016).

이 경우에 발생할 수 있습니다.

* 응용 프로그램에 현재 프로 비전 프로필을 지원 하지 않는 자격.
  가능한 해결 방법:
  - 자격을 지 원하는 다른 프로 비전 프로필을 지정 응용 프로그램 요구 사항입니다.
  - 현재 프로 비전 프로필에 지원 되지 않습니다 자격을 제거 합니다.
* 사용 하는 프로 비전 프로필에 포함 되지 않은 배포 하고자 하는 장치입니다.
  가능한 해결 방법:
  - Xcode에서 템플릿으로 새 앱을 만들고 동일한 프로 비전 프로필을 동일한 장치에 배포 합니다. 경우에 따라 Xcode은 새 장치 (Xcode에서 요청 해야 할 다른 경우)를 사용 하 여 프로 비전 프로필 고칠 수 있습니다.
  -IOS Dev Center로 이동 합니다. 새 장치를 사용 하 여 프로 비전 프로필을 업데이트 하 고 컴퓨터에 업데이트 된 프로 비전 프로필을 다운로드 합니다.

대부분의 경우 오류에 대 한 자세한 내용은 iOS 장치 로그에 표시 됩니다는 문제를 진단 하는 데 도움이 됩니다.

<a name="MT1020" />

### <a name="mt1020-failed-to-launch-the-application--on-the-device--"></a>MT1020: 응용 프로그램을 시작 하지 못했습니다 '\*'장치의'\*': *

<a name="MT1021" />

### <a name="mt1021-could-not-copy-the-file--to--2"></a>MT1021: 파일을 복사 하지 못했습니다 '\*'에'\*'. {2}

파일을 복사할 수 없습니다. 복사 작업의 오류 메시지에 오류에 대 한 자세한 정보

<a name="MT1022" />

### <a name="mt1022-could-not-copy-the-directory--to--2"></a>MT1022: 디렉터리를 복사할 수 없습니다. '\*'에'\*'. {2}

디렉터리에 복사할 수 없습니다. 복사 작업의 오류 메시지에 오류에 대 한 자세한 정보

<a name="MT1023" />

### <a name="mt1023-could-not-communicate-with-the-device-to-find-the-application---"></a>MT1023: 응용 프로그램을 확인 하려면 장치를 사용 하 여 통신할 수 없습니다 ' *': *

장치에서 응용 프로그램을 조회 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅

<a name="MT1024" />

### <a name="mt1024-the-application-signature-could-not-be-verified-on-device--please-make-sure-that-the-provisioning-profile-is-installed-and-not-expired-error-0xe8008017"></a>MT1024: 응용 프로그램 시그니처를 장치에서 확인할 수 없습니다 ' *'. 프로 비전 프로필 설치 되어 있고 만료 되지 있는지를 확인 하세요 (오류: 0xe8008017).

장치는 서명을 확인할 수 없어서 응용 프로그램 설치를 거부 합니다.

프로 비전 프로필 설치 되어 있고 만료 되지 있는지 확인 하십시오.

<a name="MT1025" />

### <a name="mt1025-could-not-list-the-crash-reports-on-the-device-"></a>MT1025: 장치에서 충돌 보고서를 나열할 수 없습니다 *.

장치에서 크래시 보고서를 나열 하는 오류가 발생 했습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1026" />

### <a name="mt1026-could-not-download-the-crash-report--from-the-device-"></a>MT1026: 충돌 보고서를 다운로드할 수 없습니다 * 장치의 * 합니다.

장치에서 충돌 보고서를 다운로드 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1027" />

### <a name="mt1027-cant-use-xcode-7-to-launch-applications-on-devices-with-ios--xcode-7-only-supports-ios-6"></a>MT1027: Xcode 7 +를 사용 하 여 ios 장치에서 응용 프로그램을 시작할 수 없습니다 * (Xcode 7은 iOS 6 이상만 지원).

6.0 이전 iOS 버전을 사용 하 여 장치에서 응용 프로그램을 시작 하려면 Xcode 7 +를 사용 하는 것이 불가능 합니다.

Xcode의 이전 버전을 사용 하거나 응용 프로그램을 시작 하려면 수동으로 앱을 탭 하세요.

<a name="MT1028" />

### <a name="mt1028-invalid-device-specification--expected-ios-watchos-or-all"></a>MT1028: 잘못 된 장치 사양: ' *'. 예상된 'ios', 'watchos' 또는 'all'.

장치 사양-를 사용 하 여 전달 된 장치가 유효 하지 않습니다. 유효한 값은: 'ios', 'watchos' 또는 'all'.

<a name="MT1029" />

### <a name="mt1029-could-not-find-an-application-at-the-specified-directory-"></a>MT1029: 지정된 된 디렉터리에서 응용 프로그램을 찾을 수 없습니다. *

-Launchdev 전달할 응용 프로그램 경로 존재 하지 않습니다. 올바른 앱 번들을 지정 하십시오.

<a name="MT1030" />

### <a name="mt1030-launching-applications-on-device-using-a-bundle-identifier-is-deprecated-please-pass-the-full-path-to-the-bundle-to-launch"></a>MT1030: 번들 식별자를 사용 하 여 장치에서 응용 프로그램을 시작 합니다. 더 이상 사용 되지 않습니다. 시작 하려면 번들에 전체 경로 전달 하세요.

앱 번들 id 대신 장치에서 시작에 대 한 경로 전달 하이 좋습니다.

<a name="MT1031" />

### <a name="mt1031-could-not-launch-the-app--on-the-device--because-the-device-is-locked-please-unlock-the-device-and-try-again"></a>MT1031: 앱을 시작할 수 없습니다 '\*'장치의'\*' 장치가 잠겨 있어. 장치의 잠금을 해제 하 고 다시 시도 하세요.

장치의 잠금을 해제 하 고 다시 시도 하세요.

<a name="MT1032" />

### <a name="mt1032-this-application-executable-might-be-too-large--mb-to-execute-on-device-if-bitcode-was-enabled-you-might-want-to-disable-it-for-development-it-is-only-required-to-submit-applications-to-apple"></a>MT1032:이 응용 프로그램 실행 파일이 너무 클 수 있습니다 (* MB) 장치에서 실행할 수 있습니다. Bitcode 사용 하도록 설정 된 개발을 위한 사용 하지 않도록 설정 하려는 경우 Apple에 응용 프로그램에 전송할만 필요 합니다.

<a name="MT1033" />

### <a name="mt1033-could-not-uninstall-the-application--from-the-device--"></a>MT1033: 응용 프로그램을 제거 하지 못했습니다 '\*'장치의'\*': *

<!-- 1034 used by mmp -->

<a name="MT1035" />

### <a name="mt1035-cannot-include-different-versions-of-the-framework-name"></a>MT1035: 서로 다른 버전의 framework '{name}'을 포함할 수 없습니다.

서로 다른 버전의 동일한 프레임 워크를 사용 하 여 연결 하는 것이 불가능 합니다.

이 문제는 일반적으로 확장 가능한 (타사 바인딩 어셈블리)를 통해 컨테이너 앱과 프레임 워크의 다른 버전을 참조할 때 발생 합니다.

다음이 오류는 여러 개 있을 [MT1036](#MT1036) 오류 각 다른 프레임 워크에 대 한 경로 나열 합니다.

<a name="MT1036" />

### <a name="mt1036-framework-name-included-from-path-related-to-previous-error"></a>MT1036: Framework '{name}'에서 포함: {path} (이전 오류 관련)

이 오류는 함께 보고 됩니다 [MT1036](#MT1036)합니다. 참조 하세요 [MT1036](#MT1036) 자세한 내용은 합니다.

### <a name="mt11xx-debug-service"></a>MT11xx: 서비스 디버그

<!--
  MT11xx DebugService.cs
  -->

<a name="MT1101" />

### <a name="mt1101-could-not-start-app"></a>MT1101: 앱을 시작할 수 없습니다.

<a name="MT1102" />

### <a name="mt1102-could-not-attach-to-the-app-to-kill-it-"></a>MT1102: 종료할) (앱에 연결 하지 못했습니다. *

<a name="MT1103" />

### <a name="mt1103-could-not-detach"></a>MT1103: 분리할 수 없습니다.

<a name="MT1104" />

### <a name="mt1104-failed-to-send-packet-"></a>MT1104: 패킷을 보내지 못했습니다. *

<a name="MT1105" />

### <a name="mt1105-unexpected-response-type"></a>MT1105: 예기치 않은 응답 형식

<a name="MT1106" />

### <a name="mt1106-could-not-get-list-of-applications-on-the-device-request-timed-out"></a>MT1106: 장치에서 응용 프로그램 목록을 가져올 수 없습니다: 요청 시간이 초과 되었습니다.

<a name="MT1107" />

### <a name="mt1107-application-failed-to-launch-"></a>MT1107: 응용 프로그램 시작 하지 못했습니다. *

장치가 잠겨 있는지 확인 하세요.

엔터프라이즈 앱을 배포 하는 경우 무료 프로 비전 프로필을 사용 해야 할 수 있습니다 개발자 신뢰 (이 대해서 설명 <a href="http://stackoverflow.com/a/30726375/183422">여기</a>).

<a name="MT1108" />

### <a name="mt1108-could-not-find-developer-tools-for-this-xx-yy-device"></a>MT1108:이 XX (YY) 장치에 대 한 개발자 도구를 찾을 수 없습니다.

Mtouch 몇 가지 작업이 필요 합니다 <tt>DeveloperDiskImage.dmg</tt> 파일이 있습니다.   이 파일 Xcode의 일부 이며 빌드를 사용 중인 SDK를 기준으로 일반적으로 위치한 합니다 <tt>Xcode.app/Contents/Developer/iPhoneOS.platform/DeviceSupport/VERSION/DeveloperDiskImage.dmg</tt>합니다.

이 오류는 연결 된 장치와 일치 하는 DeveloperDiskImage.dmg 없으므로 중 발생할 수 있습니다.

<a name="MT1109" />

### <a name="mt1109-application-failed-to-launch-because-the-device-is-locked-please-unlock-the-device-and-try-again"></a>MT1109: 응용 프로그램 장치 잠겨 있기 때문에 시작 하지 못했습니다. 장치의 잠금을 해제 하 고 다시 시도 하세요.

장치가 잠겨 있는지 확인 하세요.

<a name="MT1110" />

### <a name="mt1110-application-failed-to-launch-because-of-ios-security-restrictions-please-ensure-the-developer-is-trusted"></a>MT1110: 응용 프로그램이 iOS 보안 제한으로 인해 시작 하지 못했습니다. 개발자는 신뢰할 수 있는지 확인 하십시오.

엔터프라이즈 앱을 배포 하는 경우 무료 프로 비전 프로필을 사용 해야 할 수 있습니다 개발자 신뢰 (이 대해서 설명 <a href="http://stackoverflow.com/a/30726375/183422">여기</a>).

<a name="MT1111" />

### <a name="mt1111-application-launched-successfully-but-its-not-possible-to-wait-for-the-app-to-exit-as-requested-because-its-not-possible-to-detect-app-termination-when-launching-using-gdbserver"></a>MT1111: 응용 프로그램 실행을 성공적으로 하지만 gdbserver를 사용 하 여 시작할 때 응용 프로그램 종료를 검색 하는 것이 불가능 하기 때문에 요청한 대로 종료 하려면 앱에 대 한 대기 불가능 합니다.

### <a name="mt12xx-simulator"></a>MT12xx: 시뮬레이터

<!--
  MT12xx simcontroller.cs
  -->

<a name="MT1201" />

### <a name="mt1201-could-not-load-the-simulator-"></a>MT1201: 시뮬레이터를 로드할 수 없습니다. *

<a name="MT1202" />

### <a name="mt1202-invalid-simulator-configuration-"></a>MT1202: 잘못 된 시뮬레이터 구성: *

<a name="MT1203" />

### <a name="mt1203-invalid-simulator-specification-"></a>MT1203: 잘못 된 시뮬레이터 사양: *

<a name="MT1204" />

### <a name="mt1204-invalid-simulator-specification--runtime-not-specified"></a>MT1204: 잘못 된 시뮬레이터 사양 ' *': 런타임 지정 되지 않았습니다.

<a name="MT1205" />

### <a name="mt1205-invalid-simulator-specification--device-type-not-specified"></a>MT1205: 잘못 된 시뮬레이터 사양 ' *': 장치 유형을 지정 하지 않았습니다.

<a name="MT1206" />

### <a name="mt1206-could-not-find-the-simulator-runtime-"></a>MT1206: 시뮬레이터 런타임을 찾을 수 없습니다 ' *'.

<a name="MT1207" />

### <a name="mt1207-could-not-find-the-simulator-device-type-"></a>MT1207: 시뮬레이터 장치 유형을 찾을 수 없습니다 ' *'.

<a name="MT1208" />

### <a name="mt1208-could-not-find-the-simulator-runtime-"></a>MT1208: 시뮬레이터 런타임을 찾을 수 없습니다 ' *'.

<a name="MT1209" />

### <a name="mt1209-could-not-find-the-simulator-device-type-"></a>MT1209: 시뮬레이터 장치 유형을 찾을 수 없습니다 ' *'.

<a name="MT1210" />

### <a name="mt1210-invalid-simulator-specification--unknown-key-"></a>MT1210: 잘못 된 시뮬레이터 사양: \*, 알 수 없는 키 '\*'

<a name="MT1211" />

### <a name="mt1211-the-simulator-version--does-not-support-the-simulator-type-"></a>MT1211: 시뮬레이터 버전 '\*'시뮬레이터 형식을 지원 하지 않는'\*'

<a name="MT1212" />

### <a name="mt1212-failed-to-create-a-simulator-version-where-type---and-runtime--"></a>MT1212: 시뮬레이터 버전을 만들려면 실패 한 입력할 = * 런타임 및 = * 합니다.

<a name="MT1213" />

### <a name="mt1213-invalid-simulator-specification-for-xcode-4-"></a>MT1213: Xcode 4에 대 한 잘못 된 시뮬레이터 사양을: *

<a name="MT1214" />

### <a name="mt1214-invalid-simulator-specification-for-xcode-5-"></a>MT1214: Xcode 5에 대 한 잘못 된 시뮬레이터 사양을: *

<a name="MT1215" />

### <a name="mt1215-invalid-sdk-specified-"></a>MT1215: 지정 된 잘못 된 SDK가: *

<a name="MT1216" />

### <a name="mt1216-could-not-find-the-simulator-udid-"></a>MT1216: 시뮬레이터 UDID를 찾을 수 없습니다 ' *'.

<a name="MT1217" />

### <a name="mt1217-could-not-load-the-app-bundle-at-"></a>MT1217: 앱 번들에 로드할 수 없습니다 ' *'.

<a name="MT1218" />

### <a name="mt1218-no-bundle-identifier-found-in-the-app-at-"></a>MT1218: 앱에 있는 번들 식별자가 없는 ' *'.

<a name="MT1219" />

### <a name="mt1219-could-not-find-the-simulator-for-"></a>MT1219:에 대 한 시뮬레이터를 찾을 수 없습니다 ' *'.

<a name="MT1220" />

### <a name="mt1220-could-not-find-the-latest-simulator-runtime-for-device-"></a>MT1220: 장치에 대 한 최신 시뮬레이터 런타임을 찾을 수 없습니다 ' *'.

이 일반적으로 Xcode 사용 하 여 문제를 나타냅니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* Xcode에서 시뮬레이터를 한 번 사용 합니다.
* -Sdk를 사용 하 여 특정 SDK 버전을 전달 <version>합니다.
* Xcode를 다시 설치 합니다.

<a name="MT1221" />

### <a name="mt1221-could-not-find-the-paired-iphone-simulator-for-the-watchos-simulator-"></a>MT1221: WatchOS 시뮬레이터에 대 한 쌍을 이루는 iPhone 시뮬레이터를 찾을 수 없습니다 ' *'.

WatchOS 앱을 WatchOS 시뮬레이터에서를 시작할 때를 쌍으로 연결 된 iOS 시뮬레이터 뿐 이어야 합니다.

시뮬레이터는 iOS Xcode의 장치 UI를 사용 하 여 시뮬레이터를 사용 하 여 연결할 수 있습니다 보기 (창 메뉴-> 장치).

### <a name="mt13xx-linkwith"></a>MT13xx: [LinkWith]

<!--
  MT13xx [LinkWith]
  -->

<a name="MT1301" />

### <a name="mt1301-native-library---was-ignored-since-it-does-not-match-the-current-build-architectures-"></a>MT1301: 네이티브 라이브러리가 `*` (\*) 현재 빌드 architecture(s) 일치 하지 않기 때문에 무시 되었습니다 (\*)

<a name="MT1302" />

### <a name="mt1302-could-not-extract-the-native-library--from--please-ensure-the-native-library-was-properly-embedded-in-the-managed-assembly-if-the-assembly-was-built-using-a-binding-project-the-native-library-must-be-included-in-the-project-and-its-build-action-must-be-objcbindingnativelibrary"></a>MT1302: 네이티브 라이브러리를 추출할 수 없습니다. ' *'에서 '+'. 네이티브 라이브러리 (어셈블리 바인딩 프로젝트를 사용 하 여 빌드된, 네이티브 라이브러리 프로젝트에 포함 되어야 하 고 해당 빌드 작업 'ObjcBindingNativeLibrary' 이어야 합니다) 경우에 올바르게 관리 되는 어셈블리에 포함 된 확인 하세요.

<a name="MT1303" />

### <a name="mt1303-could-not-decompress-the-native-framework--from--please-review-the-build-log-for-more-information-from-the-native-zip-command"></a>MT1303: 네이티브 프레임 워크를 압축 하지 수 '\*'에서'\*'. Zip' 네이티브' 명령에서 자세한 정보에 대 한 빌드 로그를 검토 하세요.

바인딩 라이브러리에서 지정된 된 네이티브 프레임 워크의 압축을 풀 수 없습니다.

Zip' 네이티브' 명령에서이 오류에 대 한 자세한 내용은 bulid 로그를 검토 하세요.

<a name="MT1304" />

### <a name="mt1304-the-embedded-framework--in--is-invalid-it-does-not-contain-an-infoplist"></a>MT1304: 포함 된 프레임 워크 ' *'에서 * 잘못 되었습니다: Info.plist가 포함 되지 않습니다.

지정된 된 포함 된 프레임 워크에 Info.plist가 없는 이므로 하지 잘못 프레임 워크.

프레임 워크 올바른지 확인 하십시오.

<a name="MT1305" />

### <a name="mt1305-the-binding-library--contains-a-user-framework--but-embedded-user-frameworks-require-ios-80-the-current-deployment-target-is--please-set-the-deployment-target-in-the-infoplist-file-to-at-least-80"></a>MT1305: 바인딩 라이브러리 '\*' 사용자 프레임 워크를 포함 (\*), 포함 된 사용자 프레임 워크에는 iOS 8.0 필요 하지만 (현재 배포 대상이 *). 8.0 이상 Info.plist 파일의 배포 대상을 설정 하세요.

지정 된 바인딩 라이브러리에 포함 된 프레임 워크를 포함 하지만 Xamarin.iOS iOS 8.0 이상에 포함 된 프레임 워크를 지원 합니다.

하십시오이 오류를 해결 최소 8.0 Info.plist 파일의 배포 대상을 설정 하거나 포함 된 프레임 워크를 사용 하지 마세요.

### <a name="mt14xx-crash-reports"></a>MT14xx: 충돌 보고서

<!--
  MT14xx    CrashReports.cs
  -->

<a name="MT1400" />

### <a name="mt1400-could-not-open-crash-report-service-afcconnectionopen-returned-"></a>MT1400: 크래시 보고서 서비스를 열 수 없습니다: 반환 된 AFCConnectionOpen *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1401" />

### <a name="mt1401-could-not-close-crash-report-service-afcconnectionclose-returned-"></a>MT1401: 크래시 보고서 서비스를 닫지 못했습니다: 반환 된 AFCConnectionClose *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1402" />

### <a name="mt1402-could-not-read-file-info-for--afcfileinfoopen-returned-"></a>MT1402:에 대 한 파일 정보를 읽지 못했습니다. *: 반환 AFCFileInfoOpen *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1403" />

### <a name="mt1403-could-not-read-crash-report-afcdirectoryopen--returned-"></a>MT1403: 충돌 보고를 읽지 못했습니다: AFCDirectoryOpen (*) 반환 합니다. *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1404" />

### <a name="mt1404-could-not-read-crash-report-afcfilerefopen--returned-"></a>MT1404: 충돌 보고를 읽지 못했습니다: AFCFileRefOpen (*) 반환 합니다. *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1405" />

### <a name="mt1405-could-not-read-crash-report-afcfilerefread--returned-"></a>MT1405: 충돌 보고를 읽지 못했습니다: AFCFileRefRead (*) 반환 합니다. *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<a name="MT1406" />

### <a name="mt1406-could-not-list-crash-reports-afcdirectoryopen--returned-"></a>MT1406: 충돌 보고서를 나열할 수 없습니다: AFCDirectoryOpen (*) 반환 합니다. *

장치에서 크래시 보고서에 액세스 하려고 할 때 오류가 있습니다.

이 문제를 해결 하고자 하는 사항은 다음과 같습니다.

* 장치에서 응용 프로그램을 삭제 하 고 다시 시도 하세요.
* 장치 연결을 끊고 다시 연결 합니다.
* 장치를 다시 부팅 합니다.
* Mac을 다시 부팅
* (장치에서 작동 중단 보고를 제거 합니다) iTunes를 사용 하 여 장치를 동기화 합니다.

<!--- 1407 used by mmp -->

### <a name="mt16xx-macho"></a>MT16xx: MachO

<!--
  MT16xx    MachO.cs
  -->

<a name="MT1600" />

### <a name="mt1600-not-a-mach-o-dynamic-library-unknown-header-0x-"></a>MT1600: 하지 Mach-O 동적 라이브러리 (알 수 없는 헤더 ' 0 x *'): *.

문제의 동적 라이브러리를 처리 하는 동안 오류가 발생 했습니다.

동적 라이브러리 유효한 Mach-O 동적 라이브러리 인지 확인 하세요.

라이브러리의 형식을 사용 하 여 확인할 수 있습니다는 `file` 터미널에서 명령을 합니다.

    file -arch all -l /path/to/library.dylib

<a name="MT1601" />

### <a name="mt1601-not-a-static-library-unknown-header--"></a>MT1601: 정적 라이브러리가 아닌 (알 수 없는 헤더 ' *'): *.

해당 정적 라이브러리를 처리 하는 동안 오류가 발생 했습니다.

정적 라이브러리의 유효한 Mach-O 정적 라이브러리 인지 확인 하세요.

라이브러리의 형식을 사용 하 여 확인할 수 있습니다는 `file` 터미널에서 명령을 합니다.

    file -arch all -l /path/to/library.a

<a name="MT1602" />

### <a name="mt1602-not-a-mach-o-dynamic-library-unknown-header-0x-"></a>MT1602: 하지 Mach-O 동적 라이브러리 (알 수 없는 헤더 ' 0 x *'): *.

문제의 동적 라이브러리를 처리 하는 동안 오류가 발생 했습니다.

동적 라이브러리 유효한 Mach-O 동적 라이브러리 인지 확인 하세요.

라이브러리의 형식을 사용 하 여 확인할 수 있습니다는 `file` 터미널에서 명령을 합니다.

    file -arch all -l /path/to/library.dylib

<a name="MT1603" />

### <a name="mt1603-unknown-format-for-fat-entry-at-position--in-"></a>MT1603: 위치의 fat 항목에 대 한 알 수 없는 형식 *에서 *.

문제의 fat 보관을 처리 하는 동안 오류가 발생 했습니다.

Fat 보관 올바른지 확인 하십시오.

Fat 보관의 형식을 사용 하 여 확인할 수 있습니다는 `file` 터미널에서 명령을 합니다.

    file -arch all -l /path/to/file

<a name="MT1604" />

### <a name="mt1604-file-of-type--is-not-a-macho-file-"></a>MT1604: 형식의 파일 * 멋진 파일 (*) 아닙니다.

멋진 파일을 처리 하는 동안 오류가 발생 했습니다.

유효한 Mach-O 동적 라이브러리 파일이 있는지 확인 하십시오.

파일의 형식을 사용 하 여 확인할 수 있습니다는 `file` 터미널에서 명령을 합니다.

    file -arch all -l /path/to/file

## <a name="mt2xxx-linker-error-messages"></a>MT2xxx: 링커 오류 메시지

<!--
 MT2xxx Linker
  MT20xx Linker (general) errors
  -->

<a name="MT2001" />

### <a name="mt2001-could-not-link-assemblies"></a>MT2001: 어셈블리를 연결할 수 없습니다.

이 오류는 관리 되는 링커 예외가 예: 예기치 않은 오류가 발생 했음을 의미 하 고 완료 하거나 처리 중인 어셈블리를 저장 수 없습니다. 정확한 오류에 대 한 자세한 내용은 일부가 될 빌드 로그의 예:

```
error MT2001: Could not link assemblies.
    Method: `System.Void Todo.TodoListPageCS/<<-ctor>b__1_0>d::SetStateMachine(System.Runtime.CompilerServices.IAsyncStateMachine)`
    Assembly: `QuickTodo, Version=1.0.6297.28241, Culture=neutral, PublicKeyToken=null`
Reason: Value cannot be null.
Parameter name: instruction
```

이러한 문제에 대 한 버그 보고서를 제출 하는 것이 반드시 합니다. 대부분의 경우에는 적절 한 게시 될 때까지 해결 방법을 제공할 수 있습니다. 위의 정보는 문제를 해결 하려면 테스트 사례 및/또는 어셈블리 binairy) (함께 중요 합니다.

<a name="MT2002" />

### <a name="mt2002-can-not-resolve-reference-"></a>MT2002: 참조를 확인할 수 없습니다. *

<a name="MT2003" />

### <a name="mt2003-option--will-be-ignored-since-linking-is-disabled"></a>MT2003: 옵션 ' *' 연결 되어 있으므로 무시 됩니다.

<a name="MT2004" />

### <a name="mt2004-extra-linker-definitions-file--could-not-be-located"></a>MT2004: 추가 링커 정의 파일 ' *'를 찾을 수 없습니다.

<a name="MT2005" />

### <a name="mt2005-definitions-from--could-not-be-parsed"></a>MT2005: 정의에서 ' *'을 분석할 수 없습니다.

<a name="MT2006" />

### <a name="mt2006-can-not-load-mscorlibdll-from--please-reinstall-xamarinios"></a>MT2006:에서 mscorlib.dll을 로드할 수 없습니다. *. Xamarin.iOS를 다시 설치 하십시오.

일반적으로 이것은 Xamarin.iOS 설치에 문제가 있다는 것을 나타냅니다. Xamarin.iOS를 다시 설치 해 보세요.

<!--- 2007 used by mmp -->
<!--- 2009 used by mmp -->

<a name="MT2010" />

### <a name="mt2010-unknown-httpmessagehandler--valid-values-are-httpclienthandler-default-cfnetworkhandler-or-nsurlsessionhandler"></a>MT2010: 알 수 없는 HttpMessageHandler `*`합니다. 유효한 값은 HttpClientHandler (기본값), CFNetworkHandler 또는 NSUrlSessionHandler

<a name="MT2011" />

### <a name="mt2011-unknown-tlsprovider---valid-values-are-default-or-appletls"></a>MT2011: 알 수 없는 TlsProvider `*`합니다.  유효한 값은 기본값 appletls입니다.

에 지정 된 값 `tls-provider=` 유효한 TLS (전송 계층 보안) 공급자가 아닙니다.

합니다 `default` 및 `appletls` 만 유효한 값 및 둘 다 SSL/TLS 네이티브 Apple TLS API를 사용 하 여 지원을 제공 하는 동일한 옵션을 나타내는 됩니다.

<!--- 2012 used by mmp -->
<!--- 2013 used by mmp -->
<!--- 2014 used by mmp -->

<a name="MT2015" />

### <a name="mt2015-invalid-httpmessagehandler--for-watchos-the-only-valid-value-is-nsurlsessionhandler"></a>MT2015: 잘못 된 HttpMessageHandler `*` watchOS에 대 한 합니다. 유효한 값은 NSUrlSessionHandler.

프로젝트 파일에는 잘못 된 HttpMessageHandler 지정 하기 때문에 발생 하는 경고입니다.

프로젝트 파일에 잘못 된 값을 기본적으로 생성 하는 미리 보기 도구 버전.

이 경고를 해결 하려면 텍스트 편집기에서 프로젝트 파일을 열고 및 XML에서 모든 HttpMessageHandler 노드를 제거 합니다.

<a name="MT2016" />

### <a name="mt2016-invalid-tlsprovider-legacy-option-the-only-valid-value-appletls-will-be-used"></a>MT2016: 잘못 된 TlsProvider `legacy` 옵션입니다. 유효한 값 `appletls` 사용 됩니다.

`legacy` 공급자는 완전히 관리 되는 SSLv3 TLSv1 유일한 공급자 Xamarin.iOS를 사용 하 여 더 이상 제공 되지 /입니다. 이 이전 공급자를 사용 하 던 이제 최신를 사용 하 여 빌드할 프로젝트 `appletls` 하나입니다.

이 경고를 해결 하려면 텍스트 편집기에서 프로젝트 파일을 열고 모든 제거 ' MtouchTlsProvider ' XML에서 노드에 있습니다.

<a name="MT2017" />

### <a name="mt2017-could-not-process-xml-description"></a>MT2017: XML 설명을 처리 하지 못했습니다.

오류가 발생 하는 것을 의미 합니다 [사용자 지정 XML 링커 구성 파일](https://developer.xamarin.com/guides/cross-platform/advanced/custom_linking/) 파일 살펴보시기 제공한 합니다.

<a name="MT2018" />

### <a name="mt2018-the-assembly--is-referenced-from-two-different-locations--and-"></a>MT2018: 어셈블리 '\*' 서로 다른 두 위치에서 참조 됩니다. '\*' 및 ' *'.

오류 메시지에 언급 된 어셈블리는 여러 위치에서 로드 됩니다. 항상 동일한 버전의 어셈블리를 사용 해야 합니다.

<a name="MT2019" />

### <a name="mt2019-can-not-load-the-root-assembly-"></a>MT2019: 루트 어셈블리를 로드할 수 없습니다 ' *'

루트 어셈블리를 로드할 수 없습니다. 오류 메시지에 포함 된 경로에 기존 파일을 나타내며 유효한.NET 어셈블리 인지 확인 하십시오.

<a name="MT202x" />

### <a name="mt202x-binding-optimizer-failed-processing-"></a>MT202x: 바인딩 최적화 프로그램은 처리 하지 못했습니다. `...`합니다.

바인딩 코드 생성을 최적화 하는 동안 예기치 않은 문제가 발생 했습니다. 오류 메시지에 문제를 일으킨 요소 라고 합니다. 이라는 어셈블리 (또는 형식 또는 메서드 이름이 포함 된)이이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (예: `-v -v -v -v` 에 **추가 mtouch 인수**).

마지막 숫자임 `x` 됩니다.
* `0` 어셈블리 이름입니다.
* `1` 형식 이름입니다.
* `3` 메서드 이름입니다.

<a name="MT2030" />

### <a name="mt2030-remove-user-resources-failed-processing-"></a>MT2030: 사용자 리소스를 제거 하지 못했습니다 처리 `...`합니다.

사용자 리소스를 제거 하려고 할 때 예기치 않은 문제가 발생 했습니다. 오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

사용자 리소스는 응용 프로그램 번들을 만들려는 빌드 시 추출 해야 하는 어셈블리 (리소스로) 안에 포함 된 파일입니다. 여기에는 다음이 포함됩니다.

* `__monotouch_content_*` 및 `__monotouch_pages_*` 리소스만 및
* 네이티브 라이브러리는 바인딩 어셈블리 내에 포함

<a name="MT2040" />

### <a name="mt2040-default-httpmessagehandler-setter-failed-processing-"></a>MT2040: 기본 HttpMessageHandler setter 실패 처리 `...`합니다.

기본값을 설정 하려고 할 때 예기치 않은 문제가 발생 한 `HttpMessageHandler` 응용 프로그램에 대 한 합니다. 제출 하세요를 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (예: `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2050" />

### <a name="mt2050-code-remover-failed-processing-"></a>MT2050: 코드 remover가 처리 하지 못했습니다. `...`합니다.

응용 프로그램을 사용 하 여 전달 BCL에서 코드를 제거 하려고 할 때 예기치 않은 문제가 발생 했습니다. 제출 하세요를 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (예: `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2060" />

### <a name="mt2060-sealer-failed-processing-"></a>MT2060: Sealer 처리 하지 못했습니다. `...`합니다.

때나 devirtualizing 일부 메서드 (마지막) 형식 또는 메서드를 봉인 하는 동안 예기치 않은 문제가 발생 했습니다. 오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2070" />

### <a name="mt2070-metadata-reducer-failed-processing-"></a>MT2070: 메타 데이터 리 듀 서 처리 하지 못했습니다. `...`합니다.

응용 프로그램에서 메타 데이터를 줄이기 위해 동안 예기치 않은 문제가 발생 했습니다. 오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2080" />

### <a name="mt2080-marknsobjects-failed-processing-"></a>MT2080: MarkNSObjects 처리 하지 못했습니다. `...`합니다.

표시 하려고 할 때 예기치 않은 문제가 발생 한 `NSObject` 응용 프로그램에서 하위 클래스입니다. 오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](http://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2090" />

### <a name="mt2090-inliner-failed-processing-"></a>MT2090: 처리자 처리 하지 못했습니다. `...`합니다.

응용 프로그램에서 인라인 코드를 하려고 할 때 예기치 않은 문제가 발생 했습니다. 오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하기 위해에 제공 해야 합니다는 [버그 보고서](https://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<!-- MT21xx: more linker errors -->

<!--- 2100 used by mmp -->

<a name="MT2100" />

### <a name="mt2100-smart-enum-conversion-preserver-failed-processing-"></a>MT2100: 스마트 열거형 변환 유지 자 처리 하지 못했습니다. `...`합니다.

응용 프로그램에서 스마트 열거형에 대 한 변환 메서드를 표시 하려고 할 때 예기치 않은 문제가 발생 했습니다. 오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하기 위해에 제공 해야 합니다는 [버그 보고서](https://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2101" />

### <a name="mt2101-cant-resolve-the-reference--referenced-from-the-method--in-"></a>MT2101: 참조를 확인할 수 없습니다. '\*', 메서드에서 참조'\*'에서 ' *'.

잘못 된 어셈블리 참조는 오류 메시지에 언급 된 메서드를 처리 하는 동안 발견 되었습니다.

오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](https://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2102" />

### <a name="mt2102-error-processing-the-method--in-the-assembly--"></a>MT2102: 메서드를 처리 하는 동안 오류가 '\*'에서 어셈블리'\*': *

오류 메시지에 언급 된 메서드를 표시 하려고 할 때 예기치 않은 문제가 발생 했습니다.

오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하려면에 제공 해야 합니다는 [버그 보고서](https://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2103" />

### <a name="mt2103-error-processing-assembly--"></a>MT2103: 오류 처리 어셈블리 '\*': *

어셈블리 처리는 예기치 않은 오류가 발생 했습니다.

오류 메시지에 문제의 원인이 되는 어셈블리 이름은입니다. 어셈블리가이 문제를 해결 하기 위해에 제공 해야 합니다는 [버그 보고서](https://bugzilla.xamarin.com) 사용 하도록 설정 하는 세부 정보 표시를 사용 하 여 전체 빌드 로그와 함께 (즉 `-v -v -v -v` 에 **추가 mtouch 인수**).

<a name="MT2104" />

### <a name="mm2104-unable-to-link-assembly-0-as-it-is-mixed-mode"></a>MM2104: 어셈블리에 연결할 수 없습니다. '{0}' 혼합 모드 이므로 합니다.

링커에 의해 혼합 모드 어셈블리를 처리할 수 있습니다.

참조 https://msdn.microsoft.com/library/x0w2664k.aspx 혼합 모드 어셈블리에 대 한 자세한 내용은 합니다.

## <a name="mt3xxx-aot-error-messages"></a>MT3xxx: AOT 오류 메시지

<!--
 MT3xxx AOT
  MT30xx AOT (general) errors
  -->

<a name="MT3001" />

### <a name="mt3001-could-not-aot-the-assembly-"></a>MT3001: AOT 어셈블리 하지 못했습니다 ' *'

일반적으로이 AOT 컴파일러 버그를 나타냅니다. 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 오류를 재현 하는 프로젝트입니다.

경우에 따라 프로젝트의 iOS 빌드 옵션에서에서 증분 빌드를 사용 하지 않도록 설정 하 여이 해결할 수 있습니다 (하지만 여전히 버그를 따라서 그래도 보고 하십시오).

<a name="MT3002" />

### <a name="mt3002-aot-restriction-method--must-be-static-since-it-is-decorated-with-monopinvokecallback-see-httpsdeveloperxamarincomguidesiosadvancedtopicslimitationsreversecallbackshttpsdeveloperxamarincomguidesiosadvancedtopicslimitationsreversecallbacks"></a>MT3002: AOT 제한: 메서드 ' *' [MonoPInvokeCallback]를 사용 하 여 데코 레이트 된 하므로 정적 이어야 합니다. 참조 [https://developer.xamarin.com/guides/ios/advanced_topics/limitations/#Reverse_Callbacks](https://developer.xamarin.com/guides/ios/advanced_topics/limitations/#Reverse_Callbacks)

이 오류 메시지는 AOT 컴파일러에서 제공 됩니다.

<a name="MT3003" />

### <a name="mt3003-conflicting---debug-and---llvm-options-soft-debugging-is-disabled"></a>MT3003: 충돌-디버그 및-llvm 옵션입니다. 소프트 디버깅 사용 되지 않습니다.

LLVM 사용 하도록 설정 하면 디버깅이 지원 되지 않습니다. 응용 프로그램을 디버깅 해야 할 경우 먼저 LLVM를 비활성화 합니다.

<a name="MT3004" />

### <a name="mt3004-could-not-aot-the-assembly--because-it-doesnt-exist"></a>MT3004: AOT 어셈블리 하지 못했습니다 ' *' 없기 때문입니다.

<a name="MT3005" />

### <a name="mt3005-the-dependency--of-the-assembly--was-not-found-please-review-the-projects-references"></a>MT3005: 종속성 '\*'의 어셈블리'\*' 찾을 수 없습니다. 프로젝트의 참조를 검토 하세요.

이 문제는 일반적으로 다른 버전의 플랫폼 어셈블리 (일반적으로.NET 4 버전의 mscorlib.dll)를 참조 하는 어셈블리 경우 발생 합니다.

이 지원 되지 않습니다 하 고 수 하지 빌드하거나 제대로 실행 (어셈블리 API Xamarin.iOS 버전에 없는 mscorlib.dll의.NET 4 버전에서 사용할 수 있습니다).

<a name="MT3006" />

### <a name="mt3006-could-not-compute-a-complete-dependency-map-for-the-project-this-will-result-in-slower-build-times-because-xamarinios-cant-properly-detect-what-needs-to-be-rebuilt-and-what-does-not-need-to-be-rebuilt-please-review-previous-warnings-for-more-details"></a>MT3006: 프로젝트에 대 한 전체 종속성 맵을 계산할 수 없습니다. 이렇게 하면 빌드 시간이 느려집니다 하므로 다시 작성 하는 데 필요한 (및 다시 작성 하지 않아도 어떤) Xamarin.iOS 제대로 검색할 수 없습니다. 자세한 세부 정보에 대 한 이전 경고를 검토 하세요.

 빌드 또는 제대로 실행 (어셈블리 API Xamarin.iOS 버전에 없는 mscorlib.dll의.NET 4 버전에서 사용할 수 있습니다).

<a name="MT3007" />

### <a name="mt3007-debug-info-files-mdb-will-not-be-loaded-when-llvm-is-enabled"></a>MT3007: llvm을 사용 하는 경우 디버그 정보 파일 (*.mdb) 로드 되지 않습니다.

<a name="MT3008" />

### <a name="mt3008-bitcode-support-requires-the-use-of-the-llvm-aot-backend---llvm"></a>MT3008: Bitcode 지원 LLVM AOT 백 엔드를 사용 해야 합니다 (-llvm)

Bitcode 지원 LLVM AOT 백 엔드를 사용 해야 (-llvm).

Bitcode 지원 사용 안 함 또는 LLVM을 사용 하도록 설정 합니다.

<!--- 3009 used by mmp -->
<!--- 3010 used by mmp -->

## <a name="mt4xxx-code-generation-error-messages"></a>MT4xxx: 코드 생성 오류 메시지

### <a name="mt40xx-main"></a>MT40xx: 주

<!--
 MT4xxx code generation
  MT40xx main.m
  -->

<a name="MT4001" />

### <a name="mt4001-the-main-template-could-not-be-expanded-to-"></a>MT4001: 기본 서식 파일을 확장할 수 없습니다 `*`합니다.

Main.m 생성 오류가 발생 했습니다. 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4002" />

### <a name="mt4002-failed-to-compile-the-generated-code-for-pinvoke-methods-please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT4002: P/Invoke 메서드에 대해 생성된 된 코드를 컴파일하지 못했습니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

P/Invoke 메서드에 대해 생성된 된 코드를 컴파일하지 못했습니다. 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

### <a name="mt41xx-registrar"></a>MT41xx: 등록자

<!--
  MT41xx registrar.m
  -->

<a name="MT4101" />

### <a name="mt4101-the-registrar-cannot-build-a-signature-for-type-"></a>MT4101: 등록자 형식에 대 한 시그니처를 작성할 수 없습니다 `*`합니다.

런타임에서를 보여주기 위한 것입니다. 마샬링하는 방법을 알지는 내보낸된 API에서 형식을 찾을 수

Xamarin.iOS에는 해당 형식이 지원 해야 하는 것이 생각을 하는 경우에 향상 된 기능 요청을 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com)합니다.

<a name="MT4102" />

### <a name="mt4102-the-registrar-found-an-invalid-type--in-signature-for-method--use--instead"></a>MT4102: 등록자 찾을 잘못 `*` 메서드의 시그니처에서 `*`합니다. 대신 `*`를 사용하세요.

현재만 이런 상황이 발생 한 형식과: System.DateTime 합니다. Objective-c로 해당 (NSDate)를 대신 사용 합니다.

<a name="MT4103" />

### <a name="mt4103-the-registrar-found-an-invalid-type--in-signature-for-method--the-type-implements-inativeobject-but-does-not-have-a-constructor-that-takes-two-intptr-bool-arguments"></a>MT4103: 등록자 찾을 잘못 `*` 메서드의 시그니처에서 `*`: 형식 INativeObject를 구현 하지만 두 개를 사용 하는 생성자가 없습니다 (IntPtr, bool) 인수

이런 등록자에서 언급 한 특성을 사용 하 여 서명에서 형식 발생 하는 경우. 등록 기관은 형식의 새 인스턴스를 만들어야 할 하며이 경우 해당 (IntPtr, bool)를 사용 하 여 생성자 서명-첫 번째 인수 (IntPtr)는 호출자가 네이티브 소유권 전달 하는 경우 두 번째 관리 되는 핸들을 지정 (이 값은 '보유' 개체에서 호출 되는 false) 하는 경우를 처리 합니다.

<a name="MT4104" />

### <a name="mt4104-the-registrar-cannot-marshal-the-return-value-for-type--in-signature-for-method-"></a>MT4104: 등록자 형식에 대 한 반환 값을 마샬링할 수 없습니다 `*` 메서드의 시그니처에서 `*`합니다.

런타임에서를 보여주기 위한 것입니다. 마샬링하는 방법을 알지는 내보낸된 API에서 형식을 찾을 수

Xamarin.iOS에는 해당 형식이 지원 해야 하는 것이 생각을 하는 경우에 향상 된 기능 요청을 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com)합니다.

<a name="MT4105" />

### <a name="mt4105-the-registrar-cannot-marshal-the-parameter-of-type--in-signature-for-method-"></a>MT4105: 등록자 형식의 매개 변수를 마샬링할 수 없습니다 `*` 메서드의 시그니처에서 `*`합니다.

Xamarin.iOS에는 해당 형식이 지원 해야 하는 것이 생각을 하는 경우에 향상 된 기능 요청을 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com)합니다.

<a name="MT4106" />

### <a name="mt4106-the-registrar-cannot-marshal-the-return-value-for-structure--in-signature-for-method-"></a>MT4106: 등록자 구조에 대 한 반환 값을 마샬링할 수 없습니다 `*` 메서드의 시그니처에서 `*`합니다.

런타임에서를 보여주기 위한 것입니다. 마샬링하는 방법을 알지는 내보낸된 API에서 형식을 찾을 수

Xamarin.iOS에는 해당 형식이 지원 해야 하는 것이 생각을 하는 경우에 향상 된 기능 요청을 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com)합니다.

<a name="MT4107" />

### <a name="mt4107-the-registrar-cannot-marshal-the-parameter-of-type--in-signature-for-method-"></a>MT4107: 등록자 형식의 매개 변수를 마샬링할 수 없습니다 `*` 메서드의 시그니처에서 `+`합니다.

런타임에서를 보여주기 위한 것입니다. 마샬링하는 방법을 알지는 내보낸된 API에서 형식을 찾을 수

Xamarin.iOS에는 해당 형식이 지원 해야 하는 것이 생각을 하는 경우에 향상 된 기능 요청을 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com)합니다.

<a name="MT4108" />

### <a name="mt4108-the-registrar-cannot-get-the-objectivec-type-for-managed-type-"></a>MT4108: 등록자에 관리 되는 형식에 대 한 ObjectiveC 형식을 가져올 수 없습니다 `*`합니다.

런타임에서를 보여주기 위한 것입니다. 마샬링하는 방법을 알지는 내보낸된 API에서 형식을 찾을 수

Xamarin.iOS에는 해당 형식이 지원 해야 하는 것이 생각을 하는 경우에 향상 된 기능 요청을 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com)합니다.

<a name="MT4109" />

### <a name="mt4109-failed-to-compile-the-generated-registrar-code-please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT4109: 생성 된 등록자 코드를 컴파일하지 못했습니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

등록 기관에 대 한 생성된 된 코드를 컴파일하지 못했습니다. 빌드 로그에는 코드 컴파일 되지 이유를 설명 하는 기본 컴파일러의 출력을 포함 됩니다.

이 값은 항상 Xamarin.iOS;의 버그 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](http://bugzilla.xamarin.com) 프로젝트 또는 테스트 사례를 사용 하 여 합니다.

<a name="MT4110" />

### <a name="mt4110-the-registrar-cannot-marshal-the-out-parameter-of-type--in-signature-for-method-"></a>MT4110: 등록자 형식의 out 매개 변수를 마샬링할 수 없습니다 `*` 메서드의 시그니처에서 `*`합니다.

<a name="MT4111" />

### <a name="mt4111-the-registrar-cannot-build-a-signature-for-type--in-method-"></a>MT4111: 등록자 형식에 대 한 시그니처를 작성할 수 없습니다 `*` 메서드에서 `*`합니다.

<a name="MT4112" />

### <a name="mt4112-the-registrar-found-an-invalid-type--registering-generic-types-with-objective-c-is-not-supported-and-may-lead-to-random-behavior-andor-crashes-for-backwards-compatibility-with-older-versions-of-xamarinios-it-is-possible-to-ignore-this-error-by-passing---unsupported--enable-generics-in-registrar-as-an-additional-mtouch-argument-in-the-projects-ios-build-options-page-see-developerxamarincomguidesiosadvancedtopicsregistrarhttpsdeveloperxamarincomguidesiosadvancedtopicsregistrar-for-more-information"></a>MT4112: 등록 기관은 잘못 된 형식을 찾을 `*`합니다. 지원 되지 않습니다 Objective C를 사용 하 여 제네릭 형식을 등록 하 고 임의 동작 및/또는 충돌이 발생할 수 있습니다 (에 대 한 이전 버전과 이전 버전의 Xamarin.iOS 사용 하 여 호환성 수 있기를 전달 하 여이 오류를 무시 `--unsupported--enable-generics-in-registrar` 를 추가 mtouch로 iOS 빌드 옵션 페이지에서 프로젝트의 인수입니다. 참조 [developer.xamarin.com/guides/ios/advanced_topics/registrar](https://developer.xamarin.com/guides/ios/advanced_topics/registrar) 자세한).

<a name="MT4113" />

### <a name="mt4113-the-registrar-found-a-generic-method--exporting-generic-methods-is-not-supported-and-will-lead-to-random-behavior-andor-crashes"></a>MT4113: 등록자 제네릭 메서드를 찾을 수: '\*.\*'. 제네릭 메서드를 내보내는 지원 되지 않습니다 및 임의 동작 및/또는 크래시를 일으킵니다.

<a name="MT4114" />

### <a name="mt4114-unexpected-error-in-the-registrar-for-the-method----please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT4114: 메서드에 대 한 등록 기관에서 예기치 않은 오류 '\*.\*'-에서 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

<a name="MT4116" />

### <a name="mt4116-could-not-register-the-assembly--"></a>MT4116: 어셈블리를 등록 하지 못했습니다 ' *': *

<a name="MT4117" />

### <a name="mt4117-the-registrar-found-a-signature-mismatch-in-the-method----the-selector-indicates-the-method-takes--parameters-while-the-managed-method-has--parameters"></a>MT4117: 등록 기관에 있는 서명 불일치 메서드 '*.*'-선택기를 나타내는 메서드는 * 매개 변수를 관리 되는 메서드 동안 * 매개 변수입니다.

<a name="MT4118" />

### <a name="mt4118-cannot-register-two-managed-types--and--with-the-same-native-name-"></a>MT4118: 두 개의 관리 되는 형식을 등록할 수 없습니다 ('\*'및'\*') 같은 기본 이름을 가진 ('* ').

<a name="MT4119" />

### <a name="mt4119-could-not-register-the-selector--of-the-member--because-the-selector-is-already-registered-on-a-different-member"></a>MT4119: 선택기를 등록할 수 없습니다. '\*'의 멤버'\*. *' 선택 기가 다른 멤버에서 이미 등록 되어 있으므로.

<a name="MT4120" />

### <a name="mt4120-the-registrar-found-an-unknown-field-type--in-field--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT4120: 등록자의는 알 수 없는 필드 형식이 '\*'field' in에서\*. *'. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

이 오류는 Xamarin.iOS에서 버그를 나타냅니다. 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4121" />

### <a name="mt4121-cannot-use-gccg-to-compile-the-generated-code-from-the-static-registrar-when-using-the-accounts-framework-the-header-files-provided-by-apple-used-during-the-compilation-require-clang-either-use-clang---compilerclang-or-the-dynamic-registrar---registrardynamic"></a>MT4121: GCC를 사용할 수 없습니다 / G + + (헤더 파일을 컴파일하는 동안 사용 되는 Apple에서 제공한는 Clang 필요) 계정 프레임 워크를 사용 하는 경우 정적 등록 기관에서 생성된 된 코드를 컴파일할 수 있습니다. Clang을 사용 하거나 (-clang 컴파일러:) 또는 동적 등록 기관 (-등록자: 동적).

<a name="MT4122" />

### <a name="mt4122-cannot-use-the-clang-compiler-provided-in-the--sdk-to-compile-the-generated-code-from-the-static-registrar-when-non-ascii-type-names--are-present-in-the-application-either-use-gccg---compilergccg-the-dynamic-registrar---registrardynamic-or-a-newer-sdk"></a>MT4122:에 제공 된 Clang 컴파일러를 사용할 수 없습니다는 *합니다.* ASCII가 아닌 경우 정적 등록 기관에서 생성된 된 코드를 컴파일하는 데 SDK 형식 이름 ('* ') 응용 프로그램에 있는 합니다. GCC를 사용 하거나 / G + + (-컴파일러: gcc | g + +), 동적 등록 기관 (-등록자: 동적) 또는 최신 SDK.

<a name="MT4123" />

### <a name="mt4123-the-type-of-the-variadic-parameter-in-the-variadic-function--must-be-systemintptr"></a>MT4123: variadic 함수에는 variadic 매개 변수 형식의 ' *' System.IntPtr 이어야 합니다.

<a name="MT4124" />

### <a name="mt4124-invalid--found-on--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT4124: 잘못 된 *에 ' *'. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

이 오류는 Xamarin.iOS에서 버그를 나타냅니다. 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4125" />

### <a name="mt4125-the-registrar-found-an-invalid-type--in-signature-for-method--the-interface-must-have-a-protocol-attribute-specifying-its-wrapper-type"></a>MT4125: 등록자 찾을 잘못 된 형식 '\*'메서드의 시그니처에서'\*': 인터페이스 래퍼 형식을 지정 하는 프로토콜 특성이 있어야 합니다.

<a name="MT4126" />

### <a name="mt4126-cannot-register-two-managed-protocols--and--with-the-same-native-name-"></a>MT4126: 관리 되는 두 가지 프로토콜을 등록할 수 없습니다 ('\*'및'\*') 같은 기본 이름을 가진 ('* ').

<a name="MT4127" />

### <a name="mt4127-cannot-register-more-than-one-interface-method-for-the-method--which-is-implementing-"></a>MT4127: 메서드에 대 한 둘 이상의 인터페이스 메서드를 등록할 수 없습니다. '\*' (이 구현 하는 '\*').

<a name="MT4128" />

### <a name="mt4128-the-registrar-found-an-invalid-generic-parameter-type--in-the-method--the-generic-parameter-must-have-an-nsobject-constraint"></a>MT4128: 등록자 찾을 잘못 된 제네릭 매개 변수 형식 '\*'의 메서드'\*'. 제네릭 매개 변수는 'NSObject' 제약 조건이 있어야 합니다.

<a name="MT4129" />

### <a name="mt4129-the-registrar-found-an-invalid-generic-return-type--in-the-method--the-generic-return-type-must-have-an-nsobject-constraint"></a>MT4129: 등록자 찾을 잘못 된 제네릭 반환 형식 '\*'의 메서드'\*'. 제네릭 반환 형식에는 'NSObject' 제약 조건이 있어야 합니다.

<a name="MT4130" />

### <a name="mt4130-the-registrar-cannot-export-static-methods-in-generic-classes-"></a>MT4130: 등록자 제네릭 클래스의 정적 메서드를 내보낼 수 없습니다 ('* ').

<a name="MT4131" />

### <a name="mt4131-the-registrar-cannot-export-static-properties-in-generic-classes-"></a>MT4131: 등록자 제네릭 클래스의 정적 속성을 내보낼 수 없습니다 ('\*.\*').

<a name="MT4132" />

### <a name="mt4132-the-registrar-found-an-invalid-generic-return-type--in-the-property--the-return-type-must-have-an-nsobject-constraint"></a>MT4132: 등록자 찾을 잘못 된 제네릭 반환 형식 '\*'속성'에서\*'. 반환 형식에는 'NSObject' 제약 조건이 있어야 합니다.

<a name="MT4133" />

### <a name="mt4133-cannot-construct-an-instance-of-the-type--from-objective-c-because-the-type-is-generic-runtime-exception"></a>MT4133: 형식의 인스턴스를 생성할 수 없습니다. ' *' Objective-c에서 제네릭 형식이 이기 때문입니다. [런타임 예외가]

<a name="MT4134" />

### <a name="mt4134-your-application-is-using-the--framework-which-isnt-included-in-the-ios-sdk-youre-using-to-build-your-app-this-framework-was-introduced-in-ios--while-youre-building-with-the-ios--sdk-please-select-a-newer-sdk-in-your-apps-ios-build-options"></a>MT4134: 응용 프로그램 사용 하는 ' *' iOS 앱을 빌드하는 데 사용할 SDK에에서 포함 되어 있지는 프레임 워크 (이 프레임 워크는 iOS에서 도입 되었습니다 * iOS를 사용 하 여 빌드하는 동안, * SDK.) 앱의 iOS 빌드 옵션에서에서 최신 SDK를 선택 하세요.

<a name="MT4135" />

### <a name="mt4135-the-member--has-an-export-attribute-that-doesnt-specify-a-selector-a-selector-is-required"></a>MT4135: 멤버 '\*.\*' 선택기를 지정 하지 않는 내보내기 특성이 있습니다. 선택 기가 필요합니다.

<a name="MT4136" />

### <a name="mt4136-the-registrar-cannot-marshal-the-parameter-type--of-the-parameter--in-the-method-"></a>MT4136: 등록자 매개 변수 형식을 마샬링할 수 없습니다 '\*'의 매개 변수'\*'의 메서드'\*. *'

<!-- MT4137 is unused -->

<a name="MT4138" />

### <a name="mt4138-the-registrar-cannot-marshal-the-property-type--of-the-property-"></a>MT4138: 등록자 속성 유형을 마샬링할 수 없습니다 '\*'의 속성'\*. *'.

<a name="MT4139" />

### <a name="mt4139-the-registrar-cannot-marshal-the-property-type--of-the-property--properties-with-the-connect-attribute-must-have-a-property-type-of-nsobject-or-a-subclass-of-nsobject"></a>MT4139: 등록자 속성 유형을 마샬링할 수 없습니다 '\*'의 속성'\*. *'. [연결] 특성을 사용 하 여 속성 NSObject의 속성 형식 (또는 NSObject의 서브 클래스)에 있어야 합니다.

<a name="MT4140" />

### <a name="mt4140-the-registrar-found-a-signature-mismatch-in-the-method----the-selector-indicates-the-variadic-method-takes--parameters-while-the-managed-method-has--parameters"></a>MT4140: 등록 기관에 있는 서명 불일치 메서드 '*.*'-선택기 나타냅니다 variadic 메서드는 * 매개 변수를 관리 되는 메서드는 * 매개 변수입니다.

<a name="MT4141" />

### <a name="mt4141-cannot-register-the-selector--on-the-member--because-xamarinios-implicitly-registers-this-selector"></a>MT4141: 선택기를 등록할 수 없습니다. '\*'에 멤버'\*' Xamarin.iOS이이 선택기를 암시적으로 등록 하기 때문입니다.

이 경우에 프레임 워크 형식, 하위 클래스 지정 및는 '보유'를 구현 하는 동안 '릴리스' 또는 'dealloc' 메서드:

```csharp
class MyNSObject : NSObject
{
    [Export ("retain")]
    new void Retain () {}

    [Export ("release")]
    new void Release () {}

    [Export ("dealloc")]
    new void Dealloc () {}
}
```

그러나 클래스는 프레임 워크의 첫 번째 서브 클래스 없는 경우 이러한 메서드를 재정의 하는 가능한 형식입니다.

```csharp
class MyNSObject : NSObject
{
}

class MyCustomNSObject : MyNSObject
{
    [Export ("retain")]
    new void Retain () {}

    [Export ("release")]
    new void Release () {}

    [Export ("dealloc")]
    new void Dealloc () {}
}
```

Xamarin.iOS를 재정의 하는 경우 `retain`, `release` 및 `dealloc` 에서 `MyNSObject` 클래스와 충돌 하지 않습니다.

<a name="MT4142" />

### <a name="mt4142-failed-to-register-the-type-"></a>MT4142: 형식을 등록 하지 못했습니다 ' *'.

<a name="MT4143" />

### <a name="mt4143-the-objectivec-class--could-not-be-registered-it-does-not-seem-to-derive-from-any-known-objectivec-class-including-nsobject"></a>MT4143: ObjectiveC 클래스 ' *' 수 없는 등록에 해당 하지 않는 것 NSObject 등 모든 알려진된 ObjectiveC 클래스에서 파생 됩니다.

<a name="MT4144" />

### <a name="mt4144-cannot-register-the-method--since-it-does-not-have-an-associated-trampoline-please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT4144: 메서드를 등록할 수 없습니다. ' *'는 연결된 trampoline 없기 때문입니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com합니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4145" />

### <a name="mt4145-invalid-enum--enums-with-the-native-attribute-must-have-a-underlying-enum-type-of-either-long-or-ulong"></a>MT4145: 잘못 된 열거형 ' *': 열거형 [기본] 특성을 사용 하 여 기본 열거형 형식 'long' 또는 'ulong' 있어야 합니다.

<a name="MT4146" />

### <a name="mt4146-the-name-parameter-of-the-registrar-attribute-on-the-class---contains-an-invalid-character--"></a>MT4146:의 Name 매개 변수는 클래스에 대 한 등록자 특성\*' ('\*')에 잘못 된 문자: '\*' (\*).

Objectice C 클래스의 이름을 의미 있는 공백을 포함할 수 없습니다는 `Register` 해당 관리 되는 클래스의 특성을 사용할 수 없습니다는 `Name` 매개 변수는 하거나 공백을 포함할 수 없습니다.

있는지 확인 하십시오는 `Register` 오류 메시지에 언급 된 관리 되는 클래스의 특성은 공백을 포함할 수 없습니다.

<a name="MT4147" />

### <a name="mt4147-detected-a-protocol-inheriting-from-the-jsexport-protocol-while-using-the-dynamic-registrar-it-is-not-possible-to-export-protocols-to-javascriptcore-dynamically-the-static-registrar-must-be-used-add---registrarstatic-to-the-additional-mtouch-arguments-in-the-projects-ios-build-options-to-select-the-static-registrar"></a>MT4147: 동적 등록 기관을 사용 하는 동안 JSExport 프로토콜에서 상속 하는 프로토콜을 검색 합니다. JavaScriptCore를 프로토콜을 동적으로; 내보내려면 불가능 정적 등록 기관을 사용 해야 합니다 (추가 '-등록자: 프로젝트의 iOS 빌드 선택 옵션을 정적 등록 기관에서에서 추가 mtouch 인수에 고정).

<a name="MT4148" />

### <a name="mt4148-the-registrar-found-a-generic-protocol--exporting-generic-protocols-is-not-supported"></a>MT4148: 등록자 찾을 일반 프로토콜: ' *'. 일반 프로토콜 내보내기는 지원 되지 않습니다.

<a name="MT4149" />

### <a name="mt4149-cannot-register-the-method--because-the-type-of-the-first-parameter--does-not-match-the-category-type-"></a>MT4149: 메서드를 등록할 수 없습니다. '\*합니다.\*' 때문에 첫 번째 매개 변수의 형식 ('\*') 범주 형식과 일치 하지 않습니다 ('\*').

<a name="MT4150" />

### <a name="mt4150-cannot-register-the-type--because-the-type-property--in-its-category-attribute-does-not-inherit-from-nsobject"></a>MT4150: 유형을 등록할 수 없습니다 '\*' 때문에 Type 속성 ('\*') 해당 범주 특성에 NSObject에서 상속 되지 않습니다.

<a name="MT4151" />

### <a name="mt4151-cannot-register-the-type--because-the-type-property-in-its-category-attribute-isnt-set"></a>MT4151: 유형을 등록할 수 없습니다 ' *' 범주 특성의 Type 속성은 설정 되지 않습니다.

<a name="MT4152" />

### <a name="mt4152-cannot-register-the-type--as-a-category-because-it-implements-inativeobject-or-subclasses-nsobject"></a>MT4152: 유형을 등록할 수 없습니다 ' *' 범주로 INativeObject 또는 NSObject 서브 클래스를 구현 하므로 합니다.

<a name="MT4153" />

### <a name="mt4153-cannot-register-the-type--as-a-category-because-its-generic"></a>MT4153: 유형을 등록할 수 없습니다 '\*' 범주로 제네릭 이기 때문입니다.

<a name="MT4154" />

### <a name="mt4154-cannot-register-the-method--as-a-category-method-because-its-generic"></a>MT4154: 메서드를 등록할 수 없습니다. '\*' 범주 방법으로 제네릭 이기 때문입니다.

<a name="MT4155" />

### <a name="mt4155-cannot-register-the-method--with-the-selector--as-a-category-method-on--because-the-objective-c-already-has-an-implementation-for-this-selector"></a>MT4155: 메서드를 등록할 수 없습니다. '\*'with '선택기\*' 범주 메서드로 ' *' Objective-c이이 선택기에 대 한 구현에 이미 있으므로.

<a name="MT4156" />

### <a name="mt4156-cannot-register-two-categories--and--with-the-same-native-name-"></a>MT4156: 두 개의 범주를 등록할 수 없습니다 ('\*'및'\*') 같은 기본 이름을 가진 ('* ').

<a name="MT4157" />

### <a name="mt4157-cannot-register-the-category-method--because-at-least-one-parameter-is-required-and-its-type-must-match-the-category-type-"></a>MT4157: 범주 메서드를 등록할 수 없습니다. '\*' 매개 변수가 하나 이상 필요 하기 때문에 (형식과 범주 형식과 일치 해야 합니다 '\*')

<a name="MT4158" />

### <a name="mt4158-cannot-register-the-constructor--in-the-category--because-constructors-in-categories-are-not-supported"></a>MT4158: 생성자를 등록할 수 없습니다 * 범주에서 * 범주에는 생성자가 지원 되지 않으므로 합니다.

<a name="MT4159" />

### <a name="mt4159-cannot-register-the-method--as-a-category-method-because-category-methods-must-be-static"></a>MT4159: 메서드를 등록할 수 없습니다. ' *' 범주 메서드로 범주 메서드는 정적 이어야 하기 때문에 있습니다.

<a name="MT4160" />

### <a name="mt4160-invalid-character---found-in-selector--for-"></a>MT4160: 잘못 된 문자 '\*' (\*) 선택기 있는 '\*'for'\*'.

<a name="MT4161" />

### <a name="mt4161-the-registrar-found-an-unsupported-structure--all-fields-in-a-structure-must-also-be-structures-field--with-type-2-is-not-a-structure"></a>MT4161: 등록자는 지원 되지 않는 구조를 찾을 수 '\*': 구조체의 모든 필드에는 구조 여야 합니다. (필드 '\*'형식과'{2}' 구조가 없습니다).

등록 기관은 지원 되지 않는 필드를 사용 하 여 구조를 찾을 수 있습니다.

Objective-c에 노출 되는 구조의 모든 필드에는 구조 (클래스) 여야 합니다.

<a name="MT4162" />

### <a name="mt4162-the-type--used-as--2-is-not-available-in---it-was-introduced-in---please-build-with-a-newer--sdk-usually-done-by-using-the-most-recent-version-of-xcode"></a>MT4162: 형식을 '\*' (받았던 * {2})에서 사용할 수 없는 * * (에 도입 된 * *)\* 최신를 사용 하 여 빌드 하세요 * SDK (일반적으로 최신 버전의 Xcode 사용 하 여 수행 합니다.

등록 기관은 찾을 현재 SDK에 포함 되지 않은 형식입니다.

Xcode를 업그레이드 하세요.

<a name="MT4163" />

### <a name="mt4163-internal-error-in-the-registrar--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>등록 기관은 (*)에서 MT4163: 내부 오류입니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

이 오류는 Xamarin.iOS에서 버그를 나타냅니다. 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4164" />

### <a name="mt4164-cannot-export-the-property--because-its-selector--is-an-objective-c-keyword-please-use-a-different-name"></a>MT4164: 속성을 내보낼 수 없습니다. '\*' 때문에 해당 선택기 '\*' Objective C 키워드입니다. 다른 이름을 사용 하십시오.

해당 속성에 대 한 선택기를 유효한 Objective-c 식별자 아닙니다.

선택기로 유효한 Objective-c 식별자를 사용 하십시오.

<a name="MT4165" />

### <a name="mt4165-the-registrar-couldnt-find-the-type-systemvoid-in-any-of-the-referenced-assemblies"></a>MT4165: 등록자에서 참조 된 어셈블리의 형식 'System.Void'를 찾을 수 없습니다.

가장 가능성이 높은이 오류는 Xamarin.iOS에서 버그를 나타냅니다. 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4166" />

### <a name="mt4166-cannot-register-the-method--because-the-signature-contains-a-type--that-isnt-a-reference-type"></a>MT4166: 메서드를 등록할 수 없습니다. '\*' 시그니처에 형식 때문에 (\*) 참조 형식이 아닌입니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4167" />

### <a name="mt4167-cannot-register-the-method--because-the-signature-contains-a-generic-type--with-a-generic-argument-type-that-isnt-an-nsobject-subclass-"></a>MT4167: 메서드를 등록할 수 없습니다. '\*' 시그니처에 제네릭 형식을 때문에 (\*) (*)는 NSObject 서브 클래스에 없는 제네릭 인수 형식을 사용 하 여 합니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT4168" />

### <a name="mt4168-cannot-register-the-type-managedname-because-its-objective-c-name-exportedname-is-an-objective-c-keyword-please-use-a-different-name"></a>MT4168: 유형을 등록할 수 없습니다 ' {관리\_이름}' 때문에 Objective-c 이름 ' {내보낸\_이름}' Objective C 키워드입니다. 다른 이름을 사용 하십시오.

Objective-c로 이름을 해당 형식에 대 한 유효한 Objective-c 식별자 아닙니다.

유효한 Objective-c 식별자를 사용 하십시오.

<a name="MT4169" />

### <a name="mt4169-failed-to-generate-a-pinvoke-wrapper-for-method-message"></a>MT4169: {메서드}에 대 한 P/Invoke 래퍼를 생성 하지 못했습니다. {message}

Xamarin.iOS를 언급 한에 대 한 P/Invoke 래퍼 함수를 생성 하지 못했습니다.
근본 원인 보고 된 오류 메시지를 확인 하세요.

<a name="MT4170" />

### <a name="mt4170-the-registrar-cant-convert-from-managed-type-to-native-type-for-the-return-value-in-the-method-method"></a>MT4170: 등록자 변환할 수 없습니다 '{관리 되는 type}'에서 '{네이티브 type}' {method}의 반환 값에 대 한 합니다.

오류 설명을 참조 하세요 <a href="#MT4172">MT4172</a>합니다.

<a name="MT4171" />

### <a name="mt4171-the-bindas-attribute-on-the-member-member-is-invalid-the-bindas-type-type-is-different-from-the-property-type-type"></a>MT4171: 멤버 {멤버} BindAs 특성이 잘못 되었습니다.: BindAs {type} 형식이 {type} 속성 유형과 다릅니다.

BindAs 특성의 형식에 연결 된 멤버의 형식과 일치 하는지 확인 하세요.

<a name="MT4172" />

### <a name="mt4172-the-registrar-cant-convert-from-native-type-to-managed-type-for-the-parameter-parameter-name-in-the-method-method"></a>MT4172: 등록자 변환할 수 없습니다 '{네이티브 type}'에서 '{관리 되는 type}' 매개 변수에 대해 '{parameter name}' {method}.

등록 기관에 언급 된 형식 간 변환 하는 것을 지원 하지 않습니다.

해당 API Xamarin.iOS;에서 제공 하는 경우이 Xamarin.iOS의 버그 버그를 제출 하세요 [ http://bugzilla.xamarin.com ] [ 1]합니다.

네이티브 라이브러리에 대 한 바인딩 프로젝트를 개발 하는 동안이를 실행 하는 경우 형식의 새 조합에 대 한 지원을 추가 하기 위해 열고 죄송 합니다. 이 경우 향상 된 기능 요청을 제출 하세요 ([http://bugzilla.xamarin.com][2])를 테스트 사례를에서는 평가 합니다.

[1]: https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS
[2]: https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS&component=General&bug_severity=enhancement

## <a name="mt5xxx-gcc-and-toolchain-error-messages"></a>MT5xxx: GCC 및 도구 체인 오류 메시지

### <a name="mt51xx-compilation"></a>MT51xx: 컴파일

<!--
 MT5xxx GCC and toolchain
  MT51xx compilation
  -->

<a name="MT5101" />

### <a name="mt5101-missing--compiler-please-install-xcode-command-line-tools-component"></a>MT5101: 누락 된 ' *' 컴파일러. Xcode '명령줄 도구' 구성 요소를 설치 하세요.

<a name="MT5102" />

### <a name="mt5102-failed-to-assemble-the-file--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT5102: 파일을 어셈블할 실패 한 ' *'. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

<a name="MT5103" />

### <a name="mt5103-failed-to-compile-the-file--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT5103: 파일을 컴파일하지 못했습니다 ' *'. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

<a name="MT5104" />

### <a name="mt5104-could-not-find-neither-the--nor-the--compiler-please-install-xcode-command-line-tools-component"></a>MT5104: 찾지 모두는 '\*'또는'\*' 컴파일러. Xcode '명령줄 도구' 구성 요소를 설치 하세요.

<!-- 5105 is used by mmp -->

<a name="MT5106" />

### <a name="mt5106-could-not-compile-the-files--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT5106: 파일을 컴파일되지 수 ' *'. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

### <a name="mt52xx-linking"></a>MT52xx: 연결

<!--
  MT52xx linking
  -->

<a name="MT5201" />

### <a name="mt5201-native-linking-failed-please-review-the-build-log-and-the-user-flags-provided-to-gcc-"></a>MT5201: 네이티브 연결 하지 못했습니다. 빌드 로그 및 gcc에 제공 된 사용자 플래그를 검토 하세요. *

<a name="MT5202" />

### <a name="mt5202-native-linking-failed-please-review-the-build-log"></a>MT5202: 네이티브 연결 하지 못했습니다. 빌드 로그를 검토 하세요.

<a name="MT5203" />

### <a name="mt5203-native-linking-warning-"></a>MT5203: 연결 경고 네이티브: *

<!--- 5204-5208 are not used -->

<a name="MT5209" />

### <a name="mt5209-native-linking-error-"></a>MT5209: 네이티브 연결 오류: *

<a name="MT5210" />

### <a name="mt5210-native-linking-failed-undefined-symbol--please-verify-that-all-the-necessary-frameworks-have-been-referenced-and-native-libraries-are-properly-linked-in"></a>MT5210: 네이티브 연결 실패 정의 되지 않은 기호: *. 필요한 모든 프레임 워크 참조 된 네이티브 라이브러리에서 적절 하 게 연결 되는 확인 하십시오.

네이티브 링커가 어딘가에 참조 되는 기호를 찾을 수 없을 때 발생 합니다. 이 발생할 수 있습니다는 여러 가지가 있습니다.

* 타사 바인딩 프레임 워크를 하는데 바인딩이이 지정 하지 않으면 해당 `[LinkWith]` 특성입니다. 솔루션:
  - 타사 바인딩 작성자는 해당 원본에 액세스할 경우, 수정할 바인딩의 `[LinkWith]` 필요한 프레임 워크를 포함 하는 특성:

            [LinkWith ("mylib.a", Frameworks = "SystemConfiguration")]

  - 타사 바인딩을 수정할 수 없는 경우 수동으로 연결할 수 있습니다 필요한 프레임 워크를 사용 하 여 전달 하 여 `-gcc_flags '-framework SystemFramework'` 에 `mtouch` (프로젝트의 iOS 빌드 옵션 페이지에서 추가 mtouch 인수를 수정 하 여 수행 됩니다. 저장이 수행 해야 함을 모든 프로젝트 구성에 대 한).
* 일부 경우에는 관리 되는 바인딩 이루어집니다 여러 네이티브 라이브러리 및 모든 바인딩에 포함 되어야 합니다. 바인딩 프로젝트에 필요한 모든 네이티브 라이브러리를 단순히 추가 솔루션 이므로 각 바인딩 프로젝트에서 둘 이상의 네이티브 라이브러리를 가질 수는 것입니다.</li>
* 관리 되는 바인딩을 네이티브 라이브러리에 존재 하지 않는 네이티브 기호를 가리킵니다.
    이 문제는 일반적으로 바인딩에 일정 시간 동안 존재 하 고 네이티브 코드에 수정 되어 해당 시간 동안 특정 기본 클래스 중 하나 제거 되거나 이름이 바뀌었거나, 바인딩을 업데이트 되지 않은 동안 발생 합니다.
* P/Invoke 존재 하지 않는 네이티브 기호를 가리킵니다. Xamarin.iOS 7.4부터를 <a href="#MT5214">MT5214</a> 이 사례에 대 한 오류가 보고 됩니다 (자세한 내용은 MT5214 참조).
* 타사 바인딩 / 라이브러리를 c + +를 사용 하 여 빌드 되었지만 바인딩이이 지정 하지 않으면 해당 `[LinkWith]` 특성입니다. 이 일반적으로 매우 쉽게 인식 하도록 작업에 기호 때문에 잘못 된 c + + 기호 (한 가지 일반적인 예는 `__ZNKSt9exception4whatEv`).
  - 타사 바인딩 작성자는 해당 원본에 액세스할 경우, 수정할 바인딩의 `[LinkWith]` 특성을 설정 하는 `IsCxx` 플래그:

            [LinkWith ("mylib.a", IsCxx = true)]

  - 타사 바인딩, 수정할 수 없습니다 또는 타사 라이브러리를 사용 하 여 수동으로 연결 하는 경우 전달 하 여 해당 플래그를 설정할 수 있습니다 <code>-cxx</code> mtouch (이렇게 프로젝트의 iOS 빌드 옵션 페이지에서 추가 mtouch 인수를 수정 하려면 . 저장이 수행 해야 함을 모든 프로젝트 구성에 대 한).

<a name="MT5211" />

### <a name="mt5211-native-linking-failed-undefined-objective-c-class--the-symbol--could-not-be-found-in-any-of-the-libraries-or-frameworks-linked-with-your-application"></a>MT5211: failed 네이티브 연결을 정의 되지 않은 Objective-c 클래스: \*합니다. 기호 '\*' 라이브러리 또는 응용 프로그램을 사용 하 여 연결 된 프레임 워크 중 하나에서 찾을 수 없습니다.

네이티브 링커가 어딘가에 참조 하는 Objective-c 클래스를 찾을 수 없을 때 발생 합니다. 여러 가지 이유로 발생할 수 있습니다: 동일 [MT5210](#MT5210) 외에:

* 타사 바인딩 Objective-c 프로토콜을 바인딩 하지만 사용 하 여 주석을 지정 하지 않은 <code>[Protocol]</code> api 정의에 특성입니다. 솔루션:
  - 누락 된 추가 `[Protocol]` 특성:

              [BaseType (typeof (NSObject))]
              [Protocol] // Add this
              public interface MyProtocol
              {
              }

<a name="MT5212" />

### <a name="mt5212-native-linking-failed-duplicate-symbol-"></a>MT5212: 네이티브 연결 실패 중복 기호가: *.

네이티브 링커가 모든 네이티브 라이브러리 간에 중복 된 기호를 발견할 때 발생 합니다. 이 오류 메시지가 나타나면 있을 수 있습니다 하나 이상의 [MT5213](#MT5213) 기호의 각 항목에 대 한 위치를 사용 하 여 오류입니다. 이 오류의 원인은 다음과 같습니다.

* 동일한 네이티브 라이브러리를 두 번 포함 되어 있습니다.
* 두 개의 개별 네이티브 라이브러리는 동일한 기호를 정의 하려면 발생 합니다.
* 네이티브 라이브러리 올바르게 빌드되지, 및는 동일한 기호를 두 번 이상 포함 되어 있습니다.
  다음 터미널에서 명령 집합을 사용 하 여이 확인할 수 있습니다 (i386 x86_64/armv7/armv7s/arm64 빌드하는 아키텍처에 따라 대체):

        # Native libraries are usually fat libraries, containing binary code for
        # several architectures in the same file. First we extract the binary
        # code for the architecture we're interested in.
        lipo libNative.a -thin i386 -output libNative.i386.a

        # Now query the native library for the duplicated symbol.
        nm libNative.i386.a | fgrep 'SYMBOL'

        # You can also list the object files inside the native library.
        # In most cases this will reveal duplicated object files.
        ar -t libNative.i386.a

  이 문제를 해결 하는 몇 가지가 가지

  - 요청 네이티브 라이브러리의 공급자를 수정 하 고 업데이트 된 버전을 제공 합니다.
  - 추가 개체 파일 (이 경우에 작동 문제는 실제로 중복 된 개체 파일)를 제거 하 여 직접 해결

            # Find out if the library is a fat library, and which
            # architectures it contains.
            lipo -info libNative.a

            # Extract each architecture (i386/x86_64/armv7/armv7s/arm64) to a separate file
            lipo libNative.a -thin ARCH -output libNative.ARCH.a

            # Extract the object files for the offending architecture
            # This will remove the duplicates by overwriting them
            # (since they have the same filename)
            mkdir -p ARCH
            cd ARCH
            ar -x ../libNative.ARCH.a

            # Reassemble the object files in an .a
            ar -r ../libNative.ARCH.a *.o
            cd ..

            # Reassemble the fat library
            lipo *.a -create -output libNative.a

  - 사용 되지 않는 코드를 제거 하도록 링커에 요청 합니다. Xamarin.iOS가 이렇게 자동으로 다음 조건이 모두 충족 될 경우:
    - 모든 타사 바인딩 `[LinkWith]` 특성 SmartLink 사용 하도록 설정 합니다.

            [assembly: LinkWith ("libNative.a", SmartLink = true)]

    - 이상 `-gcc_flags` mtouch (프로젝트의 iOS 빌드 옵션의 추가 mtouch 인수 필드)에 전달 됩니다.
    - 에 직접 추가 하 여 사용 되지 않는 코드를 제거 하도록 링커에 요청할 수 이기도 `-gcc_flags -dead_strip` 추가 mtouch 인수에 ios 프로젝트의 빌드 옵션입니다.

<a name="MT5213" />

### <a name="mt5213-duplicate-symbol-in--location-related-to-previous-error"></a>MT5213: 중복 기호: * (이전 오류와 관련 된 위치)

이 오류는 함께 보고 됩니다 [MT5212](#MT5212)합니다. 참조 하세요 [MT5212](#MT5212) 자세한 내용은 합니다.

<a name="MT5214" />

### <a name="mt5214-native-linking-failed-undefined-symbol--this-symbol-was-referenced-the-managed-member--please-verify-that-all-the-necessary-frameworks-have-been-referenced-and-native-libraries-linked"></a>MT5214: 네이티브 연결 실패 정의 되지 않은 기호: *. 이 기호가 참조 된 관리 되는 멤버 * 합니다. 필요한 모든 프레임 워크 참조와 네이티브 라이브러리 연결 되었는지 확인 하세요.

이 오류는 관리 코드는 P/Invoke 존재 하지 않는 네이티브 메서드를 포함 하는 경우 보고 됩니다. 예를 들어:

```csharp
using System.Runtime.InteropServices;
class MyImports {
   [DllImport ("__Internal")]
   public static extern void MyInexistentFunc ();
}
```

가능한 해결 방법을 몇 가지 있습니다.

  -  소스 코드에서 P/Invoke 문제의 제거 합니다.
  -  (이렇게 프로젝트의 iOS 빌드 옵션에서에서 "모든 어셈블리"에 "링커 동작"을 설정 하 여) 모든 어셈블리에 대 한 관리 되는 링커를 사용 하도록 설정 합니다. 모든는 P/Invoke 사용 하지 않는 앱에서 효과적으로 제거 합니다 (자동으로 대신 수동으로 등의 이전 시점). 이렇게 하면 다소 느립니다 시뮬레이터 빌드를 리플렉션을 사용 하 여는 경우 링커에 대 한 자세한 내용은 있습니다 앱을 중단할 수 있으므로 단점은 [여기](~/ios/deploy-test/linker.md) )
  -  누락 된 네이티브 기호를 포함 하는 두 번째 네이티브 라이브러리를 만듭니다. 이 해결 방법은 단순히입니다 (해당 함수를 호출 하려는 경우, 앱 작동이 중단 됩니다).

<a name="MT5215" />

### <a name="mt5215-references-to--might-require-additional--frameworkxxx-or--lxxx-instructions-to-the-native-linker"></a>MT5215:에 대 한 참조 ' *' 추가-필요할 수 있습니다 framework = XXX 또는-lXXX 네이티브 링커가 지침

P/Invoke 라이브러리에서 참조를 검색 했지만 앱이를 사용 하 여 링크 되지 않습니다는 나타내는 경고입니다.

<a name="MT5216" />

### <a name="mt5216-native-linking-failed-for--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT5216: 네이티브 연결에 대해 실패 한 *. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com

AOT 컴파일러의 출력을 연결 하는 경우이 오류가 보고 됩니다.

가장 가능성이 높은이 오류는 Xamarin.iOS에서 버그를 나타냅니다. 버그 보고서를 제출 하세요 [ http://bugzilla.xamarin.com ](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)합니다.

<a name="MT5217" />

### <a name="mt5217-native-linking-possibly-failed-because-the-linker-command-line-was-too-long--characters"></a>MT5217: 링커 명령줄 너무 길어 실패 수 있는 네이티브 연결 (* 문자).

네이티브 연결 실패 및 링커 명령 너무 길어 발생이 불가능 합니다.

Xamarin.iOS 프로젝트는 자주 참조 네이티브 기호 동적으로 즉, 네이티브 링커가 네이티브 연결 프로세스 중 이러한 네이티브 기호를 제거할 수는 네이티브 링커가 이러한 기호를 사용 하는 보이지 않는 때문에 합니다.

일반적으로 Xamarin.iOS를 사용 하 여 이러한 기호를 그대로 유지 네이티브 링커가 묻습니다는 `-u symbol` 많은 이러한 기호를 전체 명령줄 경우 하지만 링커 플래그를 운영 체제에서 지정 된 대로 최대 명령줄 길이 초과할 수 있습니다.

이러한 동적 기호에 대 한 몇 가지 가능한 원본을 가지가 있습니다.

* P/Invoke를 정적으로 연결 된 라이브러리의 메서드 (여기서는 dll 이름 `__Internal` DllImport 특성에서 `[DllImport ("__Internal")]`).
* 바인딩 프로젝트에서 정적으로 연결 된 라이브러리의 메모리 위치에 대 한 참조를 필드 (`[Field]` 특성).
* 바인딩 프로젝트 (증분 빌드를 사용 하는 경우 또는 정적 등록자를 사용 하지 않는 경우)에서 정적으로 연결 된 라이브러리에서 참조 하는 Objective-c 클래스입니다.

가능한 해결 방법:

* 가능한 경우 SDK 어셈블리만 대신 모든 어셈블리에 대 한 관리 되는 링커를 사용 하도록 설정 합니다. 동적 기호 링커 명령줄의 되도록 하지는 최대값을 초과 대 한이 원본의 충분 한 오류를 제거할 수 있습니다.
* P/Invoke, 필드 참조 및/또는 Objective-c 클래스 수를 줄입니다.
* 동적 기호 짧은 이름에 다시 작성 합니다.
* 전달 `-dlsym:false` 프로젝트의 iOS의 추가 mtouch 인수 형태로 빌드 옵션입니다. 이 옵션을 사용 하 여 Xamarin.iOS AOT 컴파일 코드에서 네이티브 참조를 생성할 및이 기호를 유지 하도록 링커에 요청할 필요가 없습니다. 그러나 장치에 대 한이 에서만 작동 빌드 및 정적 라이브러리에 존재 하지 않는 함수에 P/Invoke 경우 링커 오류가 발생 합니다.
* 전달 `--dynamic-symbol-mode=code` 빌드 옵션으로 프로젝트의 iOS에는 추가 mtouch 인수입니다. 이 옵션을 사용 하 여 Xamarin.iOS에는 명령줄 인수를 사용 하 여 이러한 기호를 유지 하려면 네이티브 링커가 요청 하는 대신 이러한 기호를 참조 하는 추가 네이티브 코드가 생성 됩니다. 이 방식의 단점은 실행 파일의 크기를 어느 정도 증가 합니다.
* 정적 등록 기관에 전달 하 여 사용 하도록 설정 `--registrar:static` 프로젝트의 iOS의 추가 mtouch 인수 형태로 빌드 옵션 (빌드에 대 한 시뮬레이터, 장치 빌드에 대 한 정적 등록 기관에는 이미 기본값 이므로). 정적 등록 기관은 이러한 클래스를 유지 하려면 네이티브 링커가 요청 하지 않아도 되므로 Objective-c 클래스를 정적으로 참조 하는 코드를 생성 됩니다.
* (장치 빌드)를 위해 증분 빌드를 사용 하지 않도록 설정 합니다. 증분 빌드를 사용 하는 경우 정적 등록 기관에서 생성 된 코드 Xamarin.iOS 계속 유지 하도록 링커에 던져야 즉 Objective-c 클래스를 참조 하는 네이티브 링커로 간주 되지 않습니다. 따라서 증분 빌드를 사용 하지 않도록 설정 하면이 필요 없습니다.

<a name="MT5218" />

### <a name="mt5218-cant-ignore-the-dynamic-symbol-symbol---ignore-dynamic-symbolsymbol-because-it-was-not-detected-as-a-dynamic-symbol"></a>MT5218: 동적 기호 {기호}를 무시할 수 없습니다 (-무시-동적-기호 = {symbol}) 하므로 동적 기호로 시 감지 되지 않았습니다.

명령줄 인수 `--ignore-dynamic-symbol=symbol` 전달 되었지만이 기호를 수동으로 유지 해야 하는 동적 기호로 인식 된 기호가 아닌 합니다.

이 두 가지 주요 이유는

* 기호 이름이 올바르지 않습니다.
    * 기호 이름에 밑줄 앞에 추가 하지 마십시오.
    * Objective-c 클래스에 대 한 기호가 `OBJC_CLASS_$_<classname>`합니다.
* 기호 올바르지만 이미 (일부 빌드 옵션이 원인 정확한 목록을 변경 하려면 동적 기호) 하는 일반적인 방법으로 보존 되는 기호는 것입니다.

### <a name="mt53xx-other-tools"></a>다른 도구에 MT53xx:

<!--
  MT53xx other tools
  -->

<a name="MT5301" />

### <a name="mt5301-missing-strip-tool-please-install-xcode-command-line-tools-component"></a>MT5301: '제거' 도구가 없습니다. Xcode '명령줄 도구' 구성 요소를 설치 하세요.

<a name="MT5302" />

### <a name="mt5302-missing-dsymutil-tool-please-install-xcode-command-line-tools-component"></a>MT5302: 누락 된 'dsymutil' 도구입니다. Xcode '명령줄 도구' 구성 요소를 설치 하세요.

<a name="MT5303" />

### <a name="mt5303-failed-to-generate-the-debug-symbols-dsym-directory-please-review-the-build-log"></a>MT5303: 디버그 기호 (dSYM 디렉터리)를 생성 하지 못했습니다. 빌드 로그를 검토 하세요.

디버그 기호를 만들려면 최종.app 디렉터리에서 dsymutil을 실행 하는 오류가 발생 했습니다. Dsymutil의 출력을 보고 수정 방법을 참조 하세요. 빌드 로그를 검토 하세요.

<a name="MT5304" />

### <a name="mt5304-failed-to-strip-the-final-binary-please-review-the-build-log"></a>MT5304: 최종 이진 파일을 제거 하지 못했습니다. 빌드 로그를 검토 하세요.

응용 프로그램에서 디버깅 정보를 제거 하려면 '제거' 도구를 실행 하는 오류가 발생 했습니다.

<a name="MT5305" />

### <a name="mt5305-missing-lipo-tool-please-install-xcode-command-line-tools-component"></a>MT5305: 누락 된 'lipo' 도구입니다. Xcode '명령줄 도구' 구성 요소를 설치 하세요.

<a name="MT5306" />

### <a name="mt5306-failed-to-create-the-a-fat-library-please-review-the-build-log"></a>MT5306: 만들지 못했습니다.는 a fat 라이브러리입니다. 빌드 로그를 검토 하세요.

'Lipo' 도구를 실행 하는 오류가 발생 했습니다. 빌드 로그를 확인 하는 'lipo'에서 보고 한 오류를 검토 하세요.

<a name="MT5307" />

### <a name="mt5307-failed-to-sign-the-executable-please-review-the-build-log"></a>MT5307: 실행 파일을 서명 하지 못했습니다. 빌드 로그를 검토 하세요.

응용 프로그램에 서명 하는 오류가 발생 했습니다. 빌드 로그를 확인 하는 'codesign'에서 보고 한 오류를 검토 하세요.

<!-- 5308 is used by mmp -->
<!-- 5309 is used by mmp -->
<!-- 5310 is used by mmp -->

## <a name="mt6xxx-mtouch-internal-tools-error-messages"></a>MT6xxx: mtouch 내부 도구 오류 메시지

### <a name="mt600x-stripper"></a>MT600x: 제거

<!--
 MT6xxx mtouch internal tools
  MT600x Stripper
  -->

<a name="MT6001" />

### <a name="mt6001-running-version-of-cecil-doesnt-support-assembly-stripping"></a>MT6001: Cecil 실행 버전이 제거 되는 어셈블리를 지원 하지 않습니다.

<a name="MT6002" />

### <a name="mt6002-could-not-strip-assembly-"></a>MT6002: 어셈블리를 제거 하지 못했습니다 `*`합니다.

응용 프로그램에서 어셈블리에서 관리 코드 (IL 코드 제거)를 제거 하는 중 오류가 발생 했습니다.

<a name="MT6003" />

### <a name="mt6003-unauthorizedaccessexception-message"></a>MT6003: [UnauthorizedAccessException 메시지]

디버깅 응용 프로그램에서 기호를 제거 하는 동안 보안 오류가 발생 했습니다.

## <a name="mt7xxx-msbuild-error-messages"></a>MT7xxx: MSBuild 오류 메시지

<!--
 MT7xxx msbuild errors
  -->

<a name="MT7001" />

### <a name="mt7001-could-not-resolve-host-ips-for-wifi-debugger-settings"></a>MT7001: WiFi 디버거 설정에 대 한 호스트 Ip를 확인 하지 못했습니다.

*MSBuild 작업: DetectDebugNetworkConfigurationTaskBase*

문제 해결 단계

- 실행 하려고 `csharp -e 'System.Net.Dns.GetHostEntry (System.Net.Dns.GetHostName ()).AddressList'` (하는 하면 IP 주소와 오류가 분명).
- 실행 하려고 "ping \`hostname\`"는 수 제공 내용은 같은: `cannot resolve MyHost.local: Unknown host`

일부 경우에는 "로컬 네트워크" 문제 이므로 알 수 없는 호스트를 추가 하 여 해결할 수 있습니다 `127.0.0.1   MyHost.local` 에서 `/etc/hosts`합니다.

<a name="MT7002" />

### <a name="mt7002-this-machine-does-not-have-any-network-adapters-this-is-required-when-debugging-or-profiling-on-device-over-wifi"></a>MT7002:이 컴퓨터에 모든 네트워크 어댑터가 없습니다. 디버깅 또는 WiFi를 통해 장치에서 프로 파일링 하는 경우 이것이 필요 합니다.

*MSBuild 작업: DetectDebugNetworkConfigurationTaskBase*

<a name="MT7003" />

### <a name="mt7003-the-app-extension--does-not-contain-an-infoplist"></a>앱 확장을 MT7003: ' *' Info.plist가 포함 되어 있지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7004" />

### <a name="mt7004-the-app-extension--does-not-specify-a-cfbundleidentifier"></a>앱 확장을 MT7004: ' *'는 CFBundleIdentifier를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7005" />

### <a name="mt7005-the-app-extension--does-not-specify-a-cfbundleexecutable"></a>앱 확장을 MT7005: ' *'는 CFBundleExecutable를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7006" />

### <a name="mt7006-the-app-extension--has-an-invalid-cfbundleidentifier--it-does-not-begin-with-the-main-app-bundles-cfbundleidentifier-"></a>MT7006: 앱 확장 '\*'에 잘못 된 CFBundleIdentifier (\*), 기본 앱 번들의 CFBundleIdentifier (*)로 시작 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7007" />

### <a name="mt7007-the-app-extension--has-a-cfbundleidentifier--that-ends-with-the-illegal-suffix-key"></a>MT7007: 앱 확장 '\*'에 CFBundleIdentifier (\*) 잘못 되었습니다 접미사 ".key"로 끝나는 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7008" />

### <a name="mt7008-the-app-extension--does-not-specify-a-cfbundleshortversionstring"></a>앱 확장을 MT7008: ' *'는 CFBundleShortVersionString를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7009" />

### <a name="mt7009-the-app-extension--has-an-invalid-infoplist-it-does-not-contain-an-nsextension-dictionary"></a>MT7009: 앱 확장을 ' *'는 잘못 된 Info.plist에: NSExtension 사전을 포함 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7010" />

### <a name="mt7010-the-app-extension--has-an-invalid-infoplist-the-nsextension-dictionary-does-not-contain-an-nsextensionpointidentifier-value"></a>MT7010: 앱 확장을 ' *'는 잘못 된 Info.plist에: NSExtension 사전은 NSExtensionPointIdentifier 값이 포함 되지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7011" />

### <a name="mt7011-the-watchkit-extension--has-an-invalid-infoplist-the-nsextension-dictionary-does-not-contain-an-nsextensionattributes-dictionary"></a>MT7011: WatchKit 확장을 ' *'는 잘못 된 Info.plist에: NSExtension 사전에는 NSExtensionAttributes 사전이 없습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7012" />

### <a name="mt7012-the-watchkit-extension--does-not-have-exactly-one-watch-app"></a>WatchKit 확장을 MT7012: ' *'에 정확히 하나의 watch 앱이 없습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7013" />

### <a name="mt7013-the-watchkit-extension--has-an-invalid-infoplist-uirequireddevicecapabilities-must-contain-the-watch-companion-capability"></a>WatchKit 확장을 MT7013: ' *'는 잘못 된 Info.plist에: UIRequiredDeviceCapabilities ' watch 도우미 ' 기능을 포함 해야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7014" />

### <a name="mt7014-the-watch-app--does-not-contain-an-infoplist"></a>Watch 앱은 MT7014: ' *' Info.plist가 포함 되어 있지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7015" />

### <a name="mt7015-the-watch-app--does-not-specify-a-cfbundleidentifier"></a>Watch 앱은 MT7015: ' *'는 CFBundleIdentifier를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7016" />

### <a name="mt7016-the-watch-app--has-an-invalid-cfbundleidentifier--it-does-not-begin-with-the-main-app-bundles-cfbundleidentifier-"></a>MT7016: Watch 앱 '\*'에 잘못 된 CFBundleIdentifier (\*), 기본 앱 번들의 CFBundleIdentifier (*)로 시작 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7017" />

### <a name="mt7017-the-watch-app--does-not-have-a-valid-uidevicefamily-value-expected-watch-4-but-found--"></a>MT7017: Watch 앱 '\*' 유효한 UIDeviceFamily 값이 없습니다. 하는데 필요한 'Watch (4)' '\* (*)'.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7018" />

### <a name="mt7018-the-watch-app--does-not-specify-a-cfbundleexecutable"></a>Watch 앱은 MT7018: ' *'는 CFBundleExecutable를 지정 하지 않습니다

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7019" />

### <a name="mt7019-the-watch-app--has-an-invalid-wkcompanionappbundleidentifier-value--it-does-not-match-the-main-app-bundles-cfbundleidentifier-"></a>MT7019: Watch 앱 '\*' WKCompanionAppBundleIdentifier 값이 잘못 되었습니다 ('\*'), 기본 앱 번들의 CFBundleIdentifier 일치 하지 않습니다 ('* ').

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7020" />

### <a name="mt7020-the-watch-app--has-an-invalid-infoplist-the-wkwatchkitapp-key-must-be-present-and-have-a-value-of-true"></a>MT7020: Watch 앱 ' *'는 잘못 된 Info.plist에: WKWatchKitApp 키 있어야 하며 'true' 값이 있어야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7021" />

### <a name="mt7021-the-watch-app--has-an-invalid-infoplist-the-lsrequiresiphoneos-key-must-not-be-present"></a>MT7021: Watch 앱 ' *'는 잘못 된 Info.plist에: LSRequiresIPhoneOS 키 없어야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7022" />

### <a name="mt7022-the-watch-app--does-not-contain-a-watch-extension"></a>Watch 앱은 MT7022: ' *' Watch 확장을 포함 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7023" />

### <a name="mt7023-the-watch-extension--does-not-contain-an-infoplist"></a>MT7023: 조사식 확장 ' *' Info.plist가 포함 되어 있지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7024" />

### <a name="mt7024-the-watch-extension--does-not-specify-a-cfbundleidentifier"></a>MT7024: 조사식 확장 ' *'는 CFBundleIdentifier를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7025" />

### <a name="mt7025-the-watch-extension--does-not-specify-a-cfbundleexecutable"></a>MT7025: 조사식 확장 ' *'는 CFBundleExecutable를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7026" />

### <a name="mt7026-the-watch-extension--has-an-invalid-cfbundleidentifier--it-does-not-begin-with-the-main-app-bundles-cfbundleidentifier-"></a>MT7026: 조사식 확장 '\*'에 잘못 된 CFBundleIdentifier (\*), 기본 앱 번들의 CFBundleIdentifier (*)로 시작 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7027" />

### <a name="mt7027-the-watch-extension--has-a-cfbundleidentifier--that-ends-with-the-illegal-suffix-key"></a>MT7027: 조사식 확장 '\*'에 CFBundleIdentifier (\*) 잘못 되었습니다 접미사 ".key"로 끝나는 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7028" />

### <a name="mt7028-the-watch-extension--has-an-invalid-infoplist-it-does-not-contain-an-nsextension-dictionary"></a>MT7028: 조사식 확장 ' *'는 잘못 된 Info.plist에: NSExtension 사전을 포함 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7029" />

### <a name="mt7029-the-watch-extension--has-an-invalid-infoplist-the-nsextensionpointidentifier-must-be-comapplewatchkit"></a>MT7029: 조사식 확장 ' *'는 잘못 된 Info.plist에:는 NSExtensionPointIdentifier "com.apple.watchkit" 여야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7030" />

### <a name="mt7030-the-watch-extension--has-an-invalid-infoplist-the-nsextension-dictionary-must-contain-nsextensionattributes"></a>MT7030: 조사식 확장 ' *'는 잘못 된 Info.plist에: NSExtension 사전 NSExtensionAttributes 포함 해야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7031" />

### <a name="mt7031-the-watch-extension--has-an-invalid-infoplist-the-nsextensionattributes-dictionary-must-contain-a-wkappbundleidentifier"></a>MT7031: 조사식 확장 ' *'는 잘못 된 Info.plist에: NSExtensionAttributes 사전 WKAppBundleIdentifier를 포함 해야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7032" />

### <a name="mt7032-the-watchkit-extension--has-an-invalid-infoplist-uirequireddevicecapabilities-should-not-contain-the-watch-companion-capability"></a>WatchKit 확장을 MT7032: ' *'는 잘못 된 Info.plist에: UIRequiredDeviceCapabilities ' watch 도우미 ' 기능을 포함 하지 않아야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7033" />

### <a name="mt7033-the-watch-app--does-not-contain-an-infoplist"></a>Watch 앱은 MT7033: ' *' Info.plist가 포함 되어 있지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7034" />

### <a name="mt7034-the-watch-app--does-not-specify-a-cfbundleidentifier"></a>Watch 앱은 MT7034: ' *'는 CFBundleIdentifier를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7035" />

### <a name="mt7035-the-watch-app--does-not-have-a-valid-uidevicefamily-value-expected--but-found--"></a>MT7035: Watch 앱 '\*' 유효한 UIDeviceFamily 값이 없습니다. 필요한 '\*'개가 발견'\* (\*)'.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7036" />

### <a name="mt7036-the-watch-app--does-not-specify-a-cfbundleexecutable"></a>Watch 앱은 MT7036: ' *'를 CFBundleExecutable를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7037" />

### <a name="mt7037-the-watchkit-extension-extensionname-has-an-invalid-wkappbundleidentifier-value--it-does-not-match-the-watch-apps-cfbundleidentifier-"></a>MT7037: WatchKit 확장 '{extensionName}'에 잘못 된 WKAppBundleIdentifier 값 ('\*'), Watch 앱의 CFBundleIdentifier 일치 하지 않습니다 ('\*').

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7038" />

### <a name="mt7038-the-watch-app--has-an-invalid-infoplist-the-wkcompanionappbundleidentifier-must-exist-and-must-match-the-main-app-bundles-cfbundleidentifier"></a>MT7038: Watch 앱 ' *'는 잘못 된 Info.plist에:는 WKCompanionAppBundleIdentifier 존재 해야 하며 기본 앱 번들의 CFBundleIdentifier 일치 해야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7039" />

### <a name="mt7039-the-watch-app--has-an-invalid-infoplist-the-lsrequiresiphoneos-key-must-not-be-present"></a>MT7039: Watch 앱 ' *'는 잘못 된 Info.plist에: LSRequiresIPhoneOS 키 없어야 합니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7040" />

### <a name="mt7040-the-app-bundle-appbundlepath-does-not-contain-an-infoplist"></a>MT7040: 앱 번들 {AppBundlePath} Info.plist가 포함 되지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7041" />

### <a name="mt7041-main-infoplist-path-does-not-specify-a-cfbundleidentifier"></a>MT7041: 주 Info.plist 경로 CFBundleIdentifier를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7042" />

### <a name="mt7042-main-infoplist-path-does-not-specify-a-cfbundleexecutable"></a>MT7042: 주 Info.plist 경로 CFBundleExecutable를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7043" />

### <a name="mt7043-main-infoplist-path-does-not-specify-a-cfbundlesupportedplatforms"></a>MT7043: 주 Info.plist 경로 CFBundleSupportedPlatforms를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7044" />

### <a name="mt7044-main-infoplist-path-does-not-specify-a-uidevicefamily"></a>MT7044: 주 Info.plist 경로 UIDeviceFamily를 지정 하지 않습니다.

*MSBuild 작업: ValidateAppBundleTaskBase*

<a name="MT7045" />

### <a name="mt7045-unrecognized-format-"></a>MT7045: 형식을 인식할 수 없는: *.

*MSBuild 작업: PropertyListEditorTaskBase*

여기서 * 일 수 있습니다.

- string
- array
- dict
- bool
- 실수
- 정수
- date
- 데이터

<a name="MT7046" />

### <a name="mt7046-add-entry--incorrectly-specified"></a>MT7046: 추가: 항목 * 잘못 지정 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7047" />

### <a name="mt7047-add-entry--contains-invalid-array-index"></a>MT7047: 추가: 항목, *, 잘못 된 배열 인덱스를 포함 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7048" />

### <a name="mt7048-add--entry-already-exists"></a>MT7048: 추가: * 항목이 이미 있습니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7049" />

### <a name="mt7049-add-cant-add-entry--to-parent"></a>MT7049: 추가: 항목을 추가할 수 없습니다 *, 부모입니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7050" />

### <a name="mt7050-delete-cant-delete-entry--from-parent"></a>MT7050: 삭제: 항목을 삭제할 수 없습니다 *, 부모에서.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7051" />

### <a name="mt7051-delete-entry--contains-invalid-array-index"></a>MT7051: 삭제: 항목, *, 잘못 된 배열 인덱스를 포함 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7052" />

### <a name="mt7052-delete-entry--does-not-exist"></a>MT7052: 삭제: 항목, *, 존재 하지 않습니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7053" />

### <a name="mt7053-import-entry--incorrectly-specified"></a>MT7053: 가져오기: 항목 * 잘못 지정 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7054" />

### <a name="mt7054-import-entry--contains-invalid-array-index"></a>MT7054: 가져오기: 항목, *, 잘못 된 배열 인덱스를 포함 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7055" />

### <a name="mt7055-import-error-reading-file-"></a>MT7055: 가져오기: 파일 읽기 오류: *.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7056" />

### <a name="mt7056-import-cant-add-entry--to-parent"></a>MT7056: 가져오기: 항목을 추가할 수 없습니다 *, 부모입니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7057" />

### <a name="mt7057-merge-cant-add-array-entries-to-dict"></a>MT7057: 병합: dict.에 배열 항목을 추가할 수 없습니다

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7058" />

### <a name="mt7058-merge-specified-entry-must-be-a-container"></a>MT7058: 병합: 지정한 컨테이너를 입력 해야 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7059" />

### <a name="mt7059-merge-entry--contains-invalid-array-index"></a>MT7059: 병합: 항목, *, 잘못 된 배열 인덱스를 포함 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7060" />

### <a name="mt7060-merge-entry--does-not-exist"></a>MT7060: 병합: 항목 *, 존재 하지 않습니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7061" />

### <a name="mt7061-merge-error-reading-file-"></a>MT7061: 병합: 파일 읽기 오류: *.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7062" />

### <a name="mt7062-set-entry--incorrectly-specified"></a>MT7062: 설정: 항목 * 잘못 지정 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7063" />

### <a name="mt7063-set-entry--contains-invalid-array-index"></a>MT7063: 설정: 항목, *, 잘못 된 배열 인덱스를 포함 합니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7064" />

### <a name="mt7064-set-entry--does-not-exist"></a>MT7064: 설정: 항목, *, 존재 하지 않습니다.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7065" />

### <a name="mt7065-unknown-propertylist-editor-action-"></a>MT7065: 알 수 없는 PropertyList 편집기 동작: *.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7066" />

### <a name="mt7066-error-loading--"></a>MT7066: 로드 중 오류 발생 ' *': *.

*MSBuild 작업: PropertyListEditorTaskBase*

<a name="MT7067" />

### <a name="mt7067-error-saving--"></a>MT7067: 저장 오류 ' *': *.

*MSBuild 작업: PropertyListEditorTaskBase*

## <a name="mt8xxx-runtime-error-messages"></a>MT8xxx: 런타임 오류 메시지

<!--
 MT8xxx runtime
  MT800x misc
  -->

<a name="MT8001" />

### <a name="mt8001-version-mismatch-between-the-native-xamarinios-runtime-and-monotouchdll-please-reinstall-xamarinios"></a>Xamarin.iOS 런타임은 네이티브와 monotouch.dll MT8001: 버전이 일치 하지 않습니다. Xamarin.iOS를 다시 설치 하십시오.

<a name="MT8002" />

### <a name="mt8002-could-not-find-the-method--in-the-type-"></a>MT8002: 메서드를 찾을 수 없습니다 '\*'in '형식\*'.

<a name="MT8003" />

### <a name="mt8003-failed-to-find-the-closed-generic-method--on-the-type-"></a>MT8003:에서 닫힌된 제네릭 메서드를 찾지 못했습니다 '\*'유형에'\*'.

<a name="MT8004" />

### <a name="mt8004-cannot-create-an-instance-of--for-the-native-object-0x-of-type--because-another-instance-already-exists-for-this-native-object-of-type-"></a>MT8004:의 인스턴스를 만들 수 없습니다 * 네이티브 개체 0 x *에 대 한 (형식의 ' *') 이므로이 네이티브 개체에 대해 다른 인스턴스가 이미 (형식 *).

<a name="MT8005" />

### <a name="mt8005-wrapper-type--is-missing-its-native-objectivec-class-"></a>MT8005: 래퍼 형식 '\*'에 해당 네이티브 ObjectiveC 클래스 없는'\*'.

<a name="MT8006" />

### <a name="mt8006-failed-to-find-the-selector--on-the-type-"></a>MT8006: 선택기를 찾지 못했습니다 '\*'유형에'\*'

<a name="MT8007" />

### <a name="mt8007-cannot-get-the-method-descriptor-for-the-selector--on-the-type--because-the-selector-does-not-correspond-to-a-method"></a>MT8007: 선택기에 대 한 메서드 설명자를 가져올 수 없습니다 '\*'유형에'\*' 메서드에 선택기와 일치 하지 않기 때문에,

<a name="MT8008" />

### <a name="mt8008-the-loaded-version-of-xamariniosdll-was-compiled-for--bits-while-the-process-is--bits-please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8008: Xamarin.iOS.dll의 로드 된 버전에 대 한 컴파일된 * 비트 프로세스는 * 비트입니다. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

이 빌드 프로세스에서 잘못 된 것을 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8009" />

### <a name="mt8009-unable-to-locate-the-block-to-delegate-conversion-method-for-the-method-s-parameter--please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8009: 메서드에 대 한 변환 메서드를 대리자에 블록을 찾을 수 없습니다 *.*' s 매개 변수 # * 합니다. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

이 API는 올바르게 바인딩되어 되지 않은 것을 나타냅니다. 우리의 bugzilla에서 버그를 보내주세요 Xamarin에서 노출 되는 API 인 경우 ([http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS)) 타사 바인딩 경우 공급 업체에 문의 하세요.

<a name="MT8010" />

### <a name="mt8010-native-type-size-mismatch-between-xamariniosmacdll-and-the-executing-architecture-xamariniosmacdll-was-built-for--bit-while-the-current-process-is--bit"></a>Xamarin 간의 MT8010: 네이티브 형식 크기 불일치 합니다. [iOS | 실행 중인 아키텍처를 Mac].dll Xamarin입니다. [iOS | Mac].dll 용으로 빌드된 *-현재 프로세스 동안 비트 *-비트입니다.

이 빌드 프로세스에서 잘못 된 것을 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8011" />

### <a name="mt8011-unable-to-locate-the-delegate-to-block-conversion-attribute-delegateproxy-for-the-return-value-for-the-method--please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8011: 메서드에 대 한 반환 값에 대 한 블록 변환 특성 ([DelegateProxy])에 대리자를 찾을 수 없습니다 *.* 합니다. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

Xamarin.iOS (변환할 대리자 블록) 런타임에 필요한 메서드를 찾을 수 없습니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8012" />

### <a name="mt8012-invalid-delegateproxyattribute-for-the-return-value-for-the-method--delegatetype-is-null-please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8012: 메서드에 대 한 반환 값에 대 한 잘못 된 DelegateProxyAttribute *.*: DelegateType null입니다. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

해당 메서드에 대 한 DelegateProxy 특성이 올바르지 않습니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8013" />

### <a name="mt8013-invalid-delegateproxyattribute-for-the-return-value-for-the-method--delegatetype-2-specifies-a-type-without-a-handler-field-please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8013: 메서드에 대 한 반환 값에 대 한 잘못 된 DelegateProxyAttribute *합니다.*: DelegateType ({2}) 'Handler' 필드가 없으면 형식을 지정 합니다. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

해당 메서드에 대 한 DelegateProxy 특성이 올바르지 않습니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8014" />

### <a name="mt8014-invalid-delegateproxyattribute-for-the-return-value-for-the-method--the-delegatetypes-2-handler-field-is-null-please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8014: 메서드에 대 한 반환 값에 대 한 잘못 된 DelegateProxyAttribute *합니다.*: The DelegateType ({2}) 'Handler' 필드는 null입니다. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

해당 메서드에 대 한 DelegateProxy 특성이 올바르지 않습니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8015" />

### <a name="mt8015-invalid-delegateproxyattribute-for-the-return-value-for-the-method--the-delegatetypes-2-handler-field-is-not-a-delegate-its-a--please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8015: 메서드에 대 한 반환 값에 잘못 된 DelegateProxyAttribute *합니다.*: The DelegateType ({2}) 'Handler' 필드 대리자가 아니거나, 것을 *. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

해당 메서드에 대 한 DelegateProxy 특성이 올바르지 않습니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8016" />

### <a name="mt8016-unable-to-convert-delegate-to-block-for-the-return-value-for-the-method--because-the-input-isnt-a-delegate-its-a--please-file-a-bug-at-httpbugzillaxamarincom"></a>MT8016: 메서드에 대 한 반환 값에 대 한 차단 하는 대리자를 변환할 수 없습니다 *.* 입력은 대리자를 하지 않기 때문에, 것을 *. 버그를 제출 하세요 http://bugzilla.xamarin.com 합니다.

해당 메서드에 대 한 DelegateProxy 특성이 올바르지 않습니다.

일반적으로 Xamarin.iOS;의 버그를 나타냅니다이 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<!-- 8017 is used by mmp -->

<a name="MT8018" />

### <a name="mt8018-internal-consistency-error-please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT8018: 내부 일관성 오류가 발생 했습니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com 합니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8019" />

### <a name="mt8019-could-not-find-the-assembly--in-the-loaded-assemblies"></a>MT8019: 어셈블리를 찾을 수 없습니다 * 로드 된 어셈블리에 있습니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8020" />

### <a name="mt8020-could-not-find-the-module-with-metadatatoken--in-the-assembly-"></a>MT8020: MetadataToken 인 모듈을 찾을 수 없습니다 * 어셈블리의 *.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8021" />

### <a name="mt8021-unknown-implicit-token-type-"></a>MT8021: 알 수 없는 암시적 토큰 형식: *.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8022" />

### <a name="mt8022-expected-the-token-reference--to-be-a--but-its-a--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT8022: 토큰 참조를 예상 * 되도록는 *, 이지만 *입니다. 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com 합니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8023" />

### <a name="mt8023-an-instance-object-is-required-to-construct-a-closed-generic-method-for-the-open-generic-method--token-reference--please-file-a-bug-report-at-httpbugzillaxamarincom"></a>MT8023: 인스턴스 개체 오픈 제네릭 메서드의 닫힌된 제네릭 메서드를 만드는 데 필요한: * (토큰 참조: *). 버그 보고서를 제출 하세요 http://bugzilla.xamarin.com 합니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.

<a name="MT8024" />

### <a name="mt8024-could-not-find-a-valid-extension-type-for-the-smart-enum-smarttype-please-file-a-bug-at-httpsbugzillaxamarincom"></a>MT8024: 스마트 열거형 '{smart_type}'에 대 한 올바른 확장 유형이 찾을 수 없습니다. 버그를 제출 하세요 https://bugzilla.xamarin.com 합니다.

이 Xamarin.iOS에서 버그를 나타냅니다. 버그를 제출 하세요 [http://bugzilla.xamarin.com](https://bugzilla.xamarin.com/enter_bug.cgi?product=iOS) 합니다.
