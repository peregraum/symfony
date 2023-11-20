CHANGELOG for 6.4.x
===================

This changelog references the relevant changes (bug and security fixes) done
in 6.4 minor versions.

To get the diff for a specific change, go to https://github.com/symfony/symfony/commit/XXX where XXX is the change hash
To get the diff between two versions, go to https://github.com/symfony/symfony/compare/v6.4.0...v6.4.1

* 6.4.0-RC1 (2023-11-15)

 * bug #52588 [Messenger] Use extension_loaded call to check if pcntl extension is loaded, as SIGTERM might be set be swoole (Sergii Dolgushev)
 * bug #52567 [AssetMapper] Fixing js sourceMappingURL extraction when sourceMappingURL used in code (weaverryan)
 * bug #52579 [DomCrawler] UriResolver support path with colons (vdauchy)
 * bug #52581 [Messenger] attach all required parameters to query (xabbuh)
 * feature #52568 [VarExporter] Deprecate per-property lazy-initializers (nicolas-grekas)
 * feature #52560 [Mailer] Update default Mailjet port (Katario)

* 6.4.0-BETA3 (2023-11-10)

 * bug #51666 [RateLimiter] CompoundLimiter was accepting requests even when some limiters already consumed all tokens (10n)
 * bug #52524 [AssetMapper] Only download a CSS file if it is explicitly advertised (weaverryan)
 * bug #52523 [AssetMapper] avoid caching MappedAsset inside JavaScript Import (weaverryan)
 * bug #52519 [AssetMapper] If assets are served from a subdirectory or CDN, also adjust importmap keys (weaverryan)
 * bug #52508 [AssetMapper] Fix jsdelivr import parsing with no imported value (weaverryan)
 * security #cve-2023-46734 [TwigBridge] Ensure CodeExtension's filters properly escape their input (nicolas-grekas, GromNaN)
 * security #cve-2023-46735 [Webhook] Remove user-submitted type from HTTP response (nicolas-grekas)
 * security #cve-2023-46733 [Security] Fix possible session fixation when only the *token* changes (RobertMe)
 * bug #52514 [FrameworkBundle] Don't reference SYMFONY_IDE env var in non-debug mode (nicolas-grekas)
 * bug #52506 [SecurityBundle] wire the secret for Symfony 6.4 compatibility (xabbuh)
 * bug #52496 [VarDumper] Accept mixed key on `DsPairStub` (marc-mabe)
 * bug #52502 [Config] Prefixing `FileExistenceResource::__toString()` to avoid conflict with `FileResource` (weaverryan)
 * bug #52491 [String] Method toByteString conversion using iconv is unreachable (Vincentv92)
 * bug #52488 [HttpKernel] Fix PHP deprecation (nicolas-grekas)
 * bug #52469 Check whether secrets are empty and mark them all as sensitive (nicolas-grekas)
 * feature #52471 [HttpKernel] Add `ControllerResolver::allowControllers()` to define which callables are legit controllers when the `_check_controller_is_allowed` request attribute is set (nicolas-grekas)
 * bug #52476 [Messenger] fix compatibility with Doctrine DBAL 4 (xabbuh)
 * bug #52434 [Console][FrameworkBundle] Fix missing `profile` option for console commands (keulinho)
 * bug #52474 [HttpFoundation] ensure string type with mbstring func overloading enabled (xabbuh)
 * bug #52472 [HttpClient][WebProfilerBundle] Do not generate cURL command when files are uploaded (MatTheCat)
 * bug #52457 [Cache][HttpFoundation][Lock] Fix empty username/password for PDO PostgreSQL (HypeMC)
 * bug #52443 [Yaml] Fix uid binary parsing (mRoca)
 * feature #52449 [TwigBridge] Mark CodeExtension as `@internal` (fabpot)
 * bug #52429 [HttpClient] Replace `escapeshellarg` to prevent overpassing `ARG_MAX` (alexandre-daubois)
 * bug #52442 Disable the "Copy as cURL" button when the debug info are disabled (stof)
 * bug #52444 Remove full DSNs from exception messages (nicolas-grekas)
 * feature #52336 [HttpFoundation][Lock] Makes MongoDB adapters usable with `ext-mongodb` only (GromNaN)
 * bug #52428 [HttpKernel] Preventing error 500 when function putenv is disabled (ShaiMagal)
 * bug #52427 [Console][Process] do not let context classes extend the message classes (xabbuh)
 * bug #52408 [Yaml] Fix block scalar array parsing (NickSdot)
 * bug #52132 [Console] Fix horizontal table top border is incorrectly rendered (OskarStark)
 * bug #52368 [AssetMapper] Fixing bug where JSCompiler used non-absolute importmap entry path (weaverryan)
 * bug #52367 [Uid] Fix UuidV7 collisions within the same ms (nicolas-grekas)
 * bug #52287 [FrameworkBundle] Fix deprecation layer for "enable_annotations" in validation and serializer configuration (lyrixx)
 * bug #52222 [MonologBridge] Fix support for monolog 3.0 (louismariegaborit)

* 6.4.0-BETA2 (2023-10-29)

 * bug #52329 [HttpClient] Psr18Client: parse HTTP Reason Phrase for Response (Hanmac)
 * bug #52323 [AssetMapper] Allowing circular references in JavaScriptImportPathCompiler (weaverryan)
 * bug #52331 [AssetMapper] Fix file deleting errors & remove nullable MappedAsset on JS import (weaverryan)
 * bug #52332 [Yaml] Fix deprecated passing null to trim() (javaDeveloperKid)
 * bug #52349 [AssetMapper] Fix in-file imports to resolve via filesystem (weaverryan)
 * bug #52343 [Intl] Update the ICU data to 74.1 (jderusse)
 * bug #52347 [Form] Fix merging form data and files (ter) (Jan Pintr)
 * bug #52330 [AssetMapper] Fixing memory bug where we stored way more file content than needed (weaverryan)
 * bug #52325 [AssetMapper] jsdelivr "no version" import syntax (weaverryan)
 * bug #52307 [Scheduler] Save checkpoint in a finally block (FrancoisPog)
 * feature #52193 [PhpUnitBridge] Allow setting the locale using SYMFONY_PHPUNIT_LOCALE env var (VincentLanglet)
 * bug #52290 [DebugBundle] ignore a not-existing virtual request stack (xabbuh)
 * bug #52308 [SecurityBundle] Fix missing login-link element in xsd schema (fancyweb)
 * bug #51331 [Messenger] add handler description as array key to `HandlerFailedException::getWrappedExceptions()` (kbond)
 * bug #51992 [Serializer] Fix using `DateIntervalNormalizer` with union types (Jeroeny)
 * bug #52276 DB table locks on messenger_messages with many failures (bn-jdcook)
 * bug #52232 [Messenger] declare constructor argument as optional for backwards compatibility (xabbuh)
 * bug #52254 [AssetMapper] Adding import-parsing case where import contains a path (weaverryan)
 * bug #52283 [Serializer] Handle default context when denormalizing timestamps in DateTimeNormalizer (mtarld)
 * bug #52272 [VarDump] Fix order of dumped properties - parent goes first (lyrixx)
 * bug #52274 [FrameworkBundle] re-introduce conflict rule with WebProfilerBundle < 6.4 (xabbuh)
 * bug #52268 [Mailer][Notifier] Update Sendinblue / Brevo API host (Stephanie)
 * bug #52255 [Form] Skip merging params & files if there are no files in the first place (dmaicher, priyadi)
 * bug #52234  add return type hints to EntityFactory (xabbuh)
 * bug #52229 [FrameworkBundle] Fix CommandDataCollector is always registered (smnandre)
 * bug #52218 [FrameworkBundle] Add conflict with `WebProfilerBundle` < 6.4 (HeahDude)

* 6.4.0-BETA1 (2023-10-21)

 * feature #51847 [AssetMapper] Allowing for files to be written to some non-local location (weaverryan)
 * feature #52079 [HttpKernel] Add parameters `kernel.runtime_mode` and `kernel.runtime_mode.*`, all set from env var `APP_RUNTIME_MODE` (nicolas-grekas)
 * feature #51348 [FrameworkBundle][Validator] Allow implementing validation groups provider outside DTOs (Yonel Ceruto)
 * feature #51577 [Notifier][Novu] Implement overrides (wouter-toppy)
 * feature #51211 [Workflow] List place and transition listeners in profiler (lyrixx)
 * feature #51220 [Workflow] Add a `TraceableWorkflow` (lyrixx)
 * feature #52120 [AssetMapper] Split ImportmapManager into 2 (weaverryan)
 * feature #51849 [AssetMapper] Warn of missing or incompat dependencies (weaverryan)
 * feature #52032 [FrameworkBundle][Routing][Translation][Workflow] Move some compiler passes from FrameworkBundle to components (fancyweb)
 * feature #52166 [HtmlSanitizer] Add support for sanitizing unlimited length of HTML document (lyrixx)
 * feature #48095 [Messenger] [Sqs] Add `AddFifoStamp` middleware (tyx)
 * feature #52160 [DoctrineBridge] Change argument `$lastUsed` of `DoctrineTokenProvider::updateToken()` to accept `DateTimeInterface` (nicolas-grekas)
 * feature #52140 [Translation] Add argument `$buildDir` to `DataCollectorTranslator::warmUp()` (nicolas-grekas)
 * feature #52047 [HttpFoundation][Runtime] Add $flush parameter to Response::send() (fancyweb)
 * feature #51470 [FrameworkBundle][Serializer] Deprecate annotations (alexandre-daubois)
 * feature #51483 [FrameworkBundle][Routing] Deprecate annotations (alexandre-daubois)
 * feature #47416 [Console][FrameworkBundle][HttpKernel][WebProfilerBundle] Enable profiling commands (HeahDude)
 * feature #50391 [FrameworkBundle][HttpKernel] Introduce `$buildDir` argument to `WarmableInterface::warmup` to warm read-only artefacts in `build_dir` (Okhoshi)
 * feature #52087 [Scheduler] Add `FailureEvent` (alli83)
 * feature #51828 [AssetMapper] Put importmap in polyfill so it can be hosted locally easily (weaverryan)
 * feature #52024 [AssetMapper] Add a "package specifier" to importmap in case import name != package+path (weaverryan)
 * feature #50734 [ErrorHandler] Improve fileLinkFormat handling (nlemoine)
 * feature #52002 [HttpFoundation] Cookies Having Independent Partitioned State (CHIPS) (fabricecw)
 * feature #51805 [Scheduler] pre_run and post_run events (alli83)
 * feature #51926 [Mime] Forbid messages that are generators to be used more than once (fabpot)
 * feature #50946 [Routing][SecurityBundle] Add `LogoutRouteLoader` (MatTheCat)
 * feature #52038 [Console] Dispatch `ConsoleTerminateEvent` when exiting on signal (HeahDude)
 * feature #49893 [Serializer] Add `XmlEncoder::CDATA_WRAPPING` context option (AndoniLarz)
 * feature #50877 [Finder] Add early directory prunning filter support (mvorisek)
 * feature #51829 [AssetMapper] Automatically preload CSS files if WebLink available (weaverryan)
 * feature #51011 [FrameworkBundle] Add parameters deprecations to the output of `debug:container` command (HeahDude)
 * feature #51888 [WebProfiler] Profiler improvements / extract Font from stylesheet (smnandre)
 * feature #51058 [FrameworkBundle] Add `--exclude` option to the `cache:pool:clear` command (MatTheCat)
 * feature #51845 [AssetMapper] Add outdated command (Maelan LE BORGNE)
 * feature #51976 [Workflow] Revert deprecation about Registry (lyrixx)
 * feature #50537 [Console] Add placeholders to ProgressBar for exact times (maxbeckers)
 * feature #51717 [Notifier] [Telegram] Extend options for `location`, `document`, `audio`, `video`, `venue`, `photo`, `animation`, `sticker` & `contact` (igrizzli)
 * feature #49044 [Messenger] Mention the transport which failed during the setup command (thePanz)
 * feature #51786 [AssetMapper] Always downloading vendor files (weaverryan)
 * feature #51832 [DependencyInjection] Add `#[AutowireIterator]` attribute and improve `#[AutowireLocator]` (nicolas-grekas, kbond)
 * feature #50934 [Form] Add `duplicate_preferred_choices` option to `ChoiceType` (arnaud-deabreu)
 * feature #51650 [AssetMapper] Add audit command (Jean-Beru)
 * feature #51800 [DoctrineBridge] Pass `Request` to `EntityValueResolver`'s expression (HypeMC)
 * feature #51848 [Messenger] Resend failed retries back to failure transport (ro0NL)
 * feature #51811 Add "dev" keyword to symfony/symfony package (nicolas-grekas)
 * feature #51276 [Notifier] Transport possible to have null (StaffNowa)
 * feature #50662 [FrameworkBundle] Add `HttpClientAssertionsTrait` which provide shortcuts to assert HTTP calls was triggered (welcoMattic)
 * feature #50392 Move UriSigner from HttpKernel to HttpFoundation package (alexander-schranz)
 * feature #51804 [Security] Make `impersonation_path()` argument mandatory and add `impersonation_url()` (alexandre-daubois)
 * feature #50127 [TwigBridge] Add `FormLayoutTestCase` class (ker0x)
 * feature #50030 Add new twig bridge function to generate impersonation path (PhilETaylor)
 * feature #50109 [FrameworkBundle] Add --show-aliases option to debug:router command (fancyweb)
 * feature #50141 Allow sending scheduled messages through the slack API (Insanfly)
 * feature #50321 [TwigBridge] Add `AppVariable::getEnabledLocales()`  (jmsche)
 * feature #51676 [RateLimiter] Add SlidingWindowLimiter::reserve() (Jeroeny)
 * feature #51538 [HttpFoundation] Support root-level Generator in StreamedJsonResponse (Jeroeny)
 * feature #51653 [Messenger] Add WrappedExceptionsInterface for nested exceptions (Jeroeny)
 * feature #51690 [Mime] Add `TemplatedEmail::locale()` to set the locale for the email rendering (alexander-schranz)
 * feature #51525 [Messenger][Scheduler] Add AsCronTask & AsPeriodicTask attributes (valtzu)
 * feature #51795 [Scheduler] Make debug:scheduler output more useful (fabpot)
 * feature #51793 [FrameworkBundle] Change BrowserKitAssertionsTrait::getClient() to be protected (fabpot)
 * feature #44629 [FrameworkBundle] Allow BrowserKit relative URL redirect assert (julienfalque)
 * feature #51756 [Messenger] RejectRedeliveredMessageException should not be retried (nikophil)
 * feature #51779 [Serializer] Make `ProblemNormalizer` give details about Messenger’s `ValidationFailedException` (MatTheCat)
 * feature #51772 [WebProfilerBundle] Support `!` negation operator in url filter (SzymonKaminski)
 * feature #51729 [AssetMapper] Allow simple, relative paths in importmap.php (weaverryan)
 * feature #51697 [PropertyInfo] Make isWriteable() more consistent with isReadable() when checking snake_case properties (jbtronics)
 * feature #51543 [AssetMapper] Add support for CSS files in the importmap (weaverryan)
 * feature #51593 [Messenger] Add the `--all` option to the `messenger:failed:remove` command (alexandre-daubois)
 * feature #51542 [Scheduler] Trigger unique messages at runtime (Jeroeny)
 * feature #51415 [Clock] Add `DatePoint`: an immutable DateTime implementation with stricter error handling and return types (nicolas-grekas)
 * feature #51553 [Scheduler] Allow modifying the schedule at runtime and recalculate heap (Jeroeny)
 * feature #51712 Deprecate `Kernel::stripComments()` (alamirault)
 * feature #51687 [Messenger] Add support for multiple Redis Sentinel hosts (digilist)
 * feature #51153 [Translation] Add `--as-tree` option  to `translation:pull` command (syffer)
 * feature #51601 [Mime] Allow to add some headers as a strings (Oipnet)
 * feature #51684 [Translation] Give current locale to `LocaleSwitcher::runWithLocale()`'s callback (alexander-schranz)
 * feature #51651 [Scheduler] Fix stateful scheduler (valtzu)
 * feature #51638 [FrameworkBundle] [Test] add token attributes in `KernelBrowser::loginUser()` (Valmonzo)
 * feature #51558 [HttpClient] Enable using EventSourceHttpClient::connect() for both GET and POST (wivaku)
 * feature #51476 [Serializer] Allow Context to target classes (mtarld)
 * feature #50438 [Validator] Add is_valid function to Expression constraint (verdet23, DEVizzent)
 * feature #51585 [Security] Add badge resolution to profiler (Jean-Beru)
 * feature #51523 [AssetMapper] Allow specifying packages to update with importmap:update (jmsche)
 * feature #50705 [Mailer][Webhook] Add Sendgrid webhook support (WoutervanderLoopNL)
 * feature #51450 [Mailer] [Smtp] Add DSN param `peer_fingerprint` for fingerprint verification (xdavidwu)
 * feature #51484 [Workflow] deprecate `GuardEvent::getContext` method (hhamon)
 * feature #51351 [AssetMapper] Add command to download missing downloaded packages (jmsche)
 * feature #51454 [Validator] Un-deprecate passing an annotation reader to AnnotationLoader (derrabus)
 * feature #51434 [Security] [Throttling] Hide username and client ip in logs (Spomky)
 * feature #51425 [FrameworkBundle][Validator] Deprecate annotation occurrences (alexandre-daubois)
 * feature #51392 [DependencyInjection] add `#[AutowireLocator]` attribute (kbond)
 * feature #51365 [Clock] Add $modifier argument to the now() helper (nicolas-grekas)
 * feature #51327 [FrameworkBundle] Add `AbstractController::renderBlock()` and `renderBlockView()` (nicolas-grekas)
 * feature #51357 [FrameworkBundle] Deprecate not setting some options (uid, validation) (Jean-Beru)
 * feature #51325 [FrameworkBundle] Deprecate not setting some options (Jean-Beru)
 * feature #51412 [Clock] Throw `DateMalformedStringException`/`DateInvalidTimeZoneException` when appropriate (nicolas-grekas)
 * feature #51368 [DomCrawler] Added argument `$default` to method `Crawler::attr()` (Rastishka)
 * feature #51315 [Notifier][Webhook] Add Vonage support (smnandre)
 * feature #51349 [Notifier] Add GoIP bridge (ahmedghanem00)
 * feature #51332 [SecurityBundle] Deprecate the `require_previous_session` config option (alamirault)
 * feature #51284 [FrameworkBundle][HttpKernel][MonologBridge] Revisit wiring of debug loggers (nicolas-grekas)
 * feature #50306 [DomCrawler][FrameworkBundle] Add `assertAnySelectorText*` (SVillette)
 * feature #51263 [Scheduler] Add --all to debug:schedule (fabpot)
 * feature #50939 [SecurityBundle] Add `$badges` argument to `Security::login` (MatTheCat)
 * feature #50951 [FrameworkBundle] Support APP_BUILD_DIR (ro0NL)
 * feature #51264 [RemoteEvent][Webhook] Add Brevo support (blaugueux)
 * feature #50502 [RemoteEvent][Webhook] Add Mailjet support (blaugueux)
 * feature #51250 Remove remaining experimental classes (fabpot)
 * feature #51249 [RemoteEvent] Mark component as non experimental (fabpot)
 * feature #51248 [Webhook] Mark component as non experimental (fabpot)
 * feature #51247 [AssetMapper] Mark component as non experimental (fabpot)
 * feature #51246 [Scheduler] Mark component as non experimental (fabpot)
 * feature #51245 [Scheduler] Only use toString if defined for message (fabpot)
 * feature #51244 [Scheduler] Add --date to schedule:debug (fabpot)
 * feature #51210 [Workflow] Add PHP attributes to register listeners and guards (lyrixx)
 * feature #48485 [Process] Introducing a new `PhpSubprocess` handler (Toflar)
 * feature #51215 [FrameworkBundle] Enable `json_decode_detailed_errors` in dev by default (ostrolucky)
 * feature #51004 [HttpKernel] Support backed enums in `#[MapQueryParameter]` (andersmateusz)
 * feature #51230 [Scheduler] add `ScheduledStamp` to `RedispatchMessage` (kbond)
 * feature #51218 [Workflow] Support multiline descriptions in PlantUML (valtzu)
 * feature #51073 [Intl] Add support for ISO 3166-1 numeric codes (benr77)
 * feature #51191 [Mime] Update mimetypes (fabpot)
 * feature #47422 [Process] Support using `Process::findExecutable()` independently of `open_basedir` (BlackbitDevs)
 * feature #48907 [Validator] Validate time without seconds (xepozz)
 * feature #51204 [Workflow] Add a profiler (lyrixx)
 * feature #47715 [Form] Removing self-closing slash from `<input>` (ThomasLandauer)
 * feature #50212 [FrameworkBundle][Serializer] Add TranslatableNormalizer (Jean-Beru)
 * feature #50767 [HttpKernel] RequestPayloadValueResolver Add support for custom http status code (zim32)
 * feature #51172 [Serializer] Add support for seld/jsonlint (ostrolucky)
 * feature #49231 [Translation] Phrase translation provider (wickedOne)
 * feature #50974 [Workflow] Add support for storing the marking in a property (lyrixx)
 * feature #51092 [Scheduler] make `ScheduledStamp` "send-able" (kbond)
 * feature #51197 [PsrHttpMessageBridge] Support `php-http/discovery` for auto-detecting PSR-17 factories (derrabus)
 * feature #48841 [BrowserKit] Add argument $serverParameters to click() and clickLink() (syl20b)
 * feature #49594 [Serializer] Groups annotation/attribute on class (Brajk19)
 * feature #50879 [Notifier] support local development for sns by adding sslmode option (Ferror)
 * feature #51152 [Scheduler] Add `AbstractTriggerDecorator` (kbond)
 * feature #49814 [Console][Messenger] add `RunCommandMessage` and `RunCommandMessageHandler` (kbond)
 * feature #50978 [Messenger] Allow accessing all options on a handler descriptor (ruudk)
 * feature #50911 [HttpKernel] Enhance exception if possible (lyrixx)
 * feature #50136 [Notifier] [SpotHit] Support `smslong` and `smslongnbr` API parameters (camillebaronnet)
 * feature #50907 [Validator] Update `Type` constraint, add `number`, `finite-float` and `finite-number` validations (guillaume-a)
 * feature #51130 [VarDumper] Dump uninitialized properties (nicolas-grekas)
 * feature #51144 [Templating] deprecate the component (kbond)
 * feature #51014 [Mailer] Add Scaleway bridge (MrMicky-FR)
 * feature #51167 [PsrHttpMessageBridge] Remove ArgumentValueResolverInterface from PsrServerRequestResolver (derrabus)
 * feature #51100 [PsrHttpMessageBridge] Import the bridge into the monorepo (fabpot, dunglas, KorvinSzanto, xabbuh, aimeos, ahundiak, Danielss89, rougin, csunolgomez, Jérôme Parmentier, mtibben, Nyholm, ajgarlag, uphlewis, samnela, grachevko, nicolas-grekas, tinyroy, danizord, Daniel Degasperi, rbaarsma, Ekman, 4rthem, derrabus, mleczakm, iluuu1994, Tobion, chalasr, lemon-juice, franmomu, cidosx, erikn69, AurelienPillevesse)
 * feature #49815 [HttpClient][Messenger] add `PingWebhookMessage` and `PingWebhookMessageHandler` (kbond)
 * feature #49813 [Messenger][Process] add `RunProcessMessage` and `RunProcessMessageHandler` (kbond)
 * feature #51148 [FrameworkBundle] Simplify marking store configuration (nicolas-grekas)
 * feature #51128 [SecurityBundle] Allow an array of `pattern` in firewall configuration (lyrixx, chalasr)
 * feature #119 Implement ValueResolverInterface (derrabus)
 * feature #117 Leverage `Request::getPayload()` to populate the parsed body of PSR-7 requests (AurelienPillevesse)
 * feature #50931 [Form] Support Translatable Enum (Seb33300)
 * feature #49358 [Routing] Deprecate annotations in favor of attributes (derrabus)
 * feature #50982 [Validator] Deprecate annotations in favor of attributes (derrabus)
 * feature #50983 [Serializer] Deprecate annotations in favor of attributes (derrabus)
 * feature #51043 [Form] Deprecate `FormEvent::setData()` for events that do not allow it (HeahDude)
 * feature #50888 [FrameworkBundle] Deprecate doctrine/annotations integration (derrabus)
 * feature #50997 [Messenger] Deprecate `StopWorkerOnSignalsListener` (HypeMC)
 * feature #50290 [Security] Make `PersistentToken` immutable and tell `TokenProviderInterface::updateToken()` implementations should accept `DateTimeInterface` (nicolas-grekas)
 * feature #50883 [TwigBundle] Allow omitting the `autoescape_service_method` option when `autoescape_service` is set to an invokable service id (nicolas-grekas)
 * feature #50718 [DependencyInjection] Improve reporting named autowiring aliases (nicolas-grekas)
 * feature #50295 [PropertyAccess] Auto-cast from/to DateTime/Immutable when appropriate (nicolas-grekas)
 * feature #50420 [Console] add support for catching `\Throwable` errors (lyrixx)
 * feature #50148 [Mailer] Add X-Infobip-Track header to be able to disable tracking (ndousson)
 * feature #50200 [Mailer] Adds `assertEmailSubjectContains` and `assertEmailSubjectNotContains` methods (johanadivare)
 * feature #50302 [Mailer] New Brevo mailer bridge (formerly Sendinblue) (PEtanguy)
 * feature #50296 [Notifier] Add Brevo bridge (formerly Sendinblue) (PEtanguy)
 * feature #50842 Add missing return types to magic methods (wouterj)
 * feature #50868 [SecurityBundle] Deprecate `Security::*` consts and other cleanups (nicolas-grekas)
 * feature #50770 [TwigBridge] Allow to change element for `form_help` block (seb-jean)
 * feature #50814 [HttpClient] Allow custom working directory in TestHttpServer (ro0NL)
 * feature #46426 [Form] deprecate using the date and time types with date objects with not-matching timezones (xabbuh)
 * feature #50791 [DependencyInjection] Add `defined` prefix for env var processor (GaryPEGEOT)
 * feature #50754 [HttpKernel] when configuring the container add services_{env} with php extension  (helyakin)
 * feature #50425 [Validator] Allow single constraint to be passed to the `constraints` option of the `When` constraint (alexandre-daubois)
 * feature #50396 [Validator] Allow single integer for the `versions` option of the `Uuid` constraint (alexandre-daubois)
 * feature #50621 [FrameworkBundle][Workflow] Add metadata dumping support for `GraphvizDumper` (Louis-Proffit)
 * feature #50170 [Notifier] Added redlink notifier (plotkabytes)
 * feature #50615 [DependencyInjection] Deprecate `ContainerAwareInterface`, `ContainerAwareTrait` and `ContainerAwareLoader` (alexandre-daubois)
 * feature #50084 [Routing] Add FQCN and FQCN::method aliases when applicable (fancyweb)
 * feature #50691 [Console] Aligned multiline text in vertical table (jaytaph)
 * feature #50131 [Notifier] add Ntfy bridge (mikaelkael)
 * feature #50663 [Console] Add `SignalMap` to map signal value to its name (lyrixx)
 * feature #50414 [Notifier] Add Novu bridge (wouter-toppy)
 * feature #50240 [HttpClient] Add `max_retries` option to `RetryableHttpClient` (danielburger1337)
 * feature #50572 [Scheduler] Allow setting cron expression next run date timezone (danielburger1337)
 * feature #50579 [DoctrineBridge] Deprecate using the old DBAL logger system (derrabus)
 * feature #50335 [HttpKernel] Add optional `$className` param to `ControllerEvent::getAttributes()` (HypeMC)
 * feature #113 Bump psr/http-message version (erikn69)
 * feature #114 Drop support for Symfony 4 (derrabus)
 * feature #100 Allow Symfony 6 (chalasr)
 * feature #89 PSR HTTP message converters for controllers (derrabus)
 * feature #75 Remove deprecated code (fabpot)
 * feature #66 Add support for streamed Symfony request (Ekman)
 * feature #50 Add support for streamed response (danizord)
 * feature #62 bump to PHP 7.1 (nicolas-grekas)
 * feature #43 Create PSR-7 messages using PSR-17 factories (ajgarlag)
 * feature #45 Fixed broken build (Nyholm)
 * feature #1 Initial support (dunglas)
