\begin{table}[t]
    \centering
    \caption{\textbf{Main Results.} Success rates (\%) on the LIBERO and SimplerEnv (Bridge) benchmarks. * denotes reproduced results evaluated with a maximum inference horizon of 120 steps, consistent with the setting used for other models.}
    \label{tab:main}
    \resizebox{\linewidth}{!}{
    \begin{tabular}{l|cccc|c|cccc|c}
    \hline
    \multirow{2}{*}{Method} & \multicolumn{5}{c|}{LIBERO} & \multicolumn{5}{c}{SIMPLER-Env (Bridge)} \\
    \cline{2-11}
     & Spatial & Object & Goal & Long & Avg & Spoon & Carrot & Cube & Eggplant & Avg \\
    \hline
    OpenVLA~\cite{kimOpenVLAOpenSourceVisionLanguageAction2024}  & 84.7 & 88.4 & 79.2 & 53.7 & 76.5 & 4.2 & 0.0 & 8.3 & 45.8 & 14.6 \\
    OpenVLA-OFT~\cite{kim2025fine} & 96.2& 98.3& 96.2& 90.7& 95.3& - & - & - & - & - \\
    $\pi_0$~\cite{black2024pi0}  & 96.8 & 98.8 & 95.8 & 85.2 & 94.1 & 50.0 & 41.7 & 29.2 & 70.8 & 47.9 \\
    GR00T-N1~\cite{nvidia2025gr00t} & 94.4 & 97.6 & 93.0 & 90.6 & 93.9 & 64.5 & 65.5 & 5.5 & 93.0 & 57.1 \\
    $\pi_{0.5}$~\cite{blackP05VisionLanguageActionModel} & 98.8 & 98.2 & 98.0 & 92.4 & 96.9& - & - & - & - & - \\
    X-VLA*~\cite{zheng2025xvla}& 98.2 & 98.6 & 97.8 & \textbf{97.6} & 98.1& \textbf{95.8} & 75.0 & 62.5 & 70.8 & 76.0 \\
    ThinkAct~\cite{huangThinkActVisionLanguageActionReasoning2025} & 88.3 & 91.4 & 87.1 & 70.9 & 84.4 & 37.5 & 8.7 & 58.3 & 70.8 & 43.8 \\
    CoT-VLA~\cite{zhao2025cot}  & 87.5 & 91.6 & 87.6 & 69.0 & 81.1 & - & - & - & - & - \\
    Uni-VLA~\cite{wang2025unified} & 97.0 & \textbf{99.0} & 92.6 & 90.8 & 94.8 & 83.3 & 66.7 & 33.3 & \textbf{95.8} & 69.8\\
    MolmoAct~\cite{leeMolmoActActionReasoning2025} & 87.0 & 95.4 & 87.6 & 77.2 & 86.6 & - & - & - & - & - \\ 
    \hline
    GTA-VLA     &\textbf{99.0} & 98.8& \textbf{98.4} & \textbf{97.6}& \textbf{98.6}& \textbf{95.8} & \textbf{87.5} & \textbf{66.7} & 75.0 & \textbf{81.2} \\
    \hline
    \end{tabular}
    }
    \vspace{4pt}
\end{table}

 
    \begin{table}[t]
    \centering
    \caption{\textbf{OOD Generalization on SimplerEnv-Plus.} Success rates (\%) under systematic distribution shifts across visual, robot-state, language, and object-centric factors.}
    \label{tab:ood}
    \resizebox{\linewidth}{!}{
    \begin{tabular}{l|cc|cc|cc|c}
    \hline
    \multirow{2}{*}{Method} & \multicolumn{2}{c|}{Visual} & \multicolumn{1}{c|}{Robot} & \multicolumn{1}{c|}{Language} & \multicolumn{2}{c|}{Objects} & \multirow{2}{*}{Avg} \\
\cline{2-7}
& Sensor & Lighting & \multicolumn{1}{c|}{State} & \multicolumn{1}{c|}{Diversity} & Unseen Obj. & Distractor & \\

    \hline
    OpenVLA~\cite{kimOpenVLAOpenSourceVisionLanguageAction2024} & 5.2 & 6.3 & 0.0 & 8.3 & 2.1 & 0.0 & 3.7\\
    % GR00T-N1~\cite{nvidia2025gr00t} & & & & & & & \\
    $\pi_{0.5}$~\cite{blackP05VisionLanguageActionModel} & 9.4 & 10.4 & 9.4 & 8.3 & 6.3 & 0.0 & 7.3\\
    % E-CoT~\cite{zawalskiRoboticControlEmbodied2025a} & & & & & & & \\
    X-VLA~\cite{zheng2025xvla} & 27.1 & 68.8 & 68.7 & 66.3 & 36.2 & 46.9 & 52.3\\
    \hline
    GTA-VLA & 39.6 & 76.1 & 79.2 & 68.1 &  58.3 &  50.0 & 61.4\\
    \hline
    \end{tabular}
    }
    \end{table}

    \begin{table}[t]
    \centering
    \caption{Effectiveness of Visual Guidance in Ambiguous Scenarios. We evaluate different input modalities for our model on challenging SimplerEnv-Plus tasks. All values are success rates (\%). Visual guidance significantly outperforms even dense linguistic instructions, especially when spatial ambiguity is high.}
    \label{tab:guidance_efficacy}
    \resizebox{\columnwidth}{!}{%
    \begin{tabular}{l|ccc|c||cc|c}
    \toprule
    \multirow{2}{*}{\textbf{Guidance Modality}} & \multicolumn{4}{c|}{\textbf{Unseen Object Ambiguity}} & \multicolumn{3}{c}{\textbf{Distractor-based Ambiguity}} \\
    \cmidrule(r){2-5} \cmidrule(l){6-8}
     & Unseen Toy & Unseen Fruit & Unseen Tool & \textbf{Avg.} & Color Distractor & Pos. Distractor & \textbf{Avg.} \\
    \midrule
    Dense Instruction ($\pi_{0.5}$) & 8.3 & 12.5 & 8.3 & 9.7 & 8.3 & 8.3 & 8.3\\
    Dense Instruction(GTA-VLA) & 12.5 & 41.6 & 29.2 & 27.8 & 45.8 & 29.2 &  37.5\\
    \midrule
    \rowcolor{gray!20}
    + Visual Point Guide & 33.3 & 47.9 & 41.6 & 40.9 & 58.3 & 50.0 & 54.2\\
    \rowcolor{gray!20}
    + Visual Box Guide & 54.1 & 70.8 & 45.8 &  56.9 & 41.6 & 45.8 & 43.7\\
    \bottomrule
    \end{tabular}
    }
    \end{table}
    