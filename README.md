Data Code (DC) is an acoustic-based data transmission protocol designed to turn structured computer program source code and textual sequences directly into modulated audio waveforms. By mapping character strings, mathematical operations, numbers, and logical markers directly to unique audio signatures, it facilitates data-over-sound serialization similar to early dial-up modem infrastructures.
The accompanying program, Data Code Generator (DCG), is a Tkinter-based compiler engine that translates multi-line inputs into standard 16-bit linear PCM .wav containers while generating real-time telemetry processing logs.

1. Protocol Dictionary Mapping

The transmission matrix below defines the strict frequency properties, structural time shifts, and wave topologies assigned to each syntax token within the Data Code specification.

Alphabetic Characters


Token	Structural Representation	Audio Waveform Type	Parameter Value(s)	Signal Duration
A	:_'	Sinusoidal Beep	1000 Hz	0.10 seconds
B	[]+0	Intermittent Time Delay	1000 Hz (2.0s Pause)	2.10 seconds
C	[]+1	Intermittent Time Delay	1000 Hz (1.0s Pause)	1.10 seconds
D	|>o	Frequency Multi-Tone Sequence	[400 Hz, 800 Hz]	0.15 seconds
E	.*.	Low-Frequency Modulated Beep	300 Hz	0.10 seconds
F	~/_	Frequency Multi-Tone Sequence	[500 Hz, 1000 Hz, 500 Hz]	0.10 seconds
G	##=	Frequency Shift Trill	1200 Hz Base	0.30 seconds
H	^/^	Spaced Sequence Multi-Tone	[1500 Hz, 1500 Hz] (1.0s Pause)	1.16 seconds
I	!_!	High-Pitch Transient Chirp	1800 Hz	0.04 seconds
J	_/_	Spaced Sequence Multi-Tone	[300 Hz, 1200 Hz] (2.0s Pause)	2.16 seconds
K	<->	Transient Click Sequence	1000 Hz Interspersed	0.10 seconds
L	|\_	Continuous Sustained Tone	1000 Hz	1.00 seconds
M	^^^	Frequency Multi-Tone Sequence	[300 Hz, 300 Hz, 300 Hz]	0.15 seconds
N	\\\	Frequency Multi-Tone Sequence	[800 Hz, 800 Hz, 800 Hz]	0.15 seconds
O	(0)	Phase-Shift Dual Ring	880 Hz / 885 Hz Blend	0.40 seconds
P	*_*	Transient Click Sequence	600 Hz Interspersed	0.10 seconds
Q	?/	White Noise Static Burst	Non-Periodic White Noise	0.20 seconds
R	/~/	Spaced Sequence Multi-Tone	[1000 Hz, 400 Hz] (1.0s Pause)	1.16 seconds
S	===	White Noise Hiss Band	Low-Amplitude Noise	0.50 seconds
T	_|_	Frequency Multi-Tone Sequence	[200 Hz, 1200 Hz]	0.15 seconds
U	v_v	Frequency Multi-Tone Sequence	[1400 Hz, 1400 Hz]	0.05 seconds
V	\/	Spaced Sequence Multi-Tone	[400 Hz, 400 Hz] (1.0s Pause)	1.16 seconds
W	vvv	Frequency Multi-Tone Sequence	[1400 Hz, 1400 Hz, 1400 Hz]	0.05 seconds
X	%+%	Segmented Static Double Burst	Noise-Silence-Noise	0.30 seconds
Y	_-_	Frequency Multi-Tone Sequence	[400 Hz, 1600 Hz]	0.15 seconds
Z	z_z	Linear Sawtooth Buzz	120 Hz Sawtooth	0.40 seconds


Numeric Tokens


Token	Audio Waveform Type	Frequency Value	Signal Duration
0	Sinusoidal Beep	500 Hz	0.10 seconds
1	Sinusoidal Beep	550 Hz	0.10 seconds
2	Sinusoidal Beep	600 Hz	0.10 seconds
3	Sinusoidal Beep	650 Hz	0.10 seconds
4	Sinusoidal Beep	700 Hz	0.10 seconds
5	Sinusoidal Beep	750 Hz	0.10 seconds
6	Sinusoidal Beep	800 Hz	0.10 seconds
7	Sinusoidal Beep	850 Hz	0.10 seconds
8	Sinusoidal Beep	900 Hz	0.10 seconds
9	Sinusoidal Beep	950 Hz	0.10 seconds


Syntax & Logical Operators


Token	Escaped Character	Audio Waveform Type	Parameter Value(s)	Signal Duration
[Space]	' '	Low-Duration Boundary Silence	Zero-Amplitude Stream	0.20 seconds
[Newline]	\n	Frequency Multi-Tone Sequence	[200 Hz, 300 Hz, 400 Hz]	0.30 seconds
[Tab]	\t	High-Duration Structural Silence	Zero-Amplitude Stream	0.50 seconds
=	=	Frequency Multi-Tone Sequence	[600 Hz, 600 Hz]	0.10 seconds
+	+	Frequency Multi-Tone Sequence	[700 Hz, 900 Hz]	0.15 seconds
-	-	Frequency Multi-Tone Sequence	[900 Hz, 700 Hz]	0.15 seconds
*** **	*	Frequency Shift Trill	1500 Hz Base	0.20 seconds
/	/	White Noise Static Burst	Non-Periodic White Noise	0.10 seconds
(	(	Sinusoidal Beep	1300 Hz	0.08 seconds
)	)	Sinusoidal Beep	1100 Hz	0.08 seconds
"	"	Transient Click Sequence	2000 Hz Interspersed	0.05 seconds
'	'	Transient Click Sequence	2200 Hz Interspersed	0.05 seconds
:	:	Frequency Multi-Tone Sequence	[1200 Hz, 1200 Hz]	0.10 seconds
,	,	Sinusoidal Beep	400 Hz	0.05 seconds
!	!	White Noise Static Burst	Non-Periodic White Noise	0.05 seconds


System Telemetry Tokens


Token	Audio Waveform Type	Frequency Sweep Vector	Signal Duration
<EOF>	Linear Frequency Modulation Siren	400 Hz scaling to 1200 Hz	1.50 seconds


2. Technical Execution Mechanics


1. Frame Separation Boundaries

To maintain structural parsing integrity and prevent inter-symbol interference (ISI) caused by lingering audio echoes, the compiler architecture inserts a physical 10-millisecond frame boundary separation block (zero-amplitude array padding) between every processed character vector.

2. Multi-Threading Logging Pattern

To prevent user interface thread suspension during intensive multi-second file-writing tasks, compilation operations invoke a secondary execution thread (threading.Thread). The background process communicates with the foreground console layout through cross-thread safe event mechanisms (root.after).
