{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 179,
   "id": "2a329e47-54f9-4537-a6e3-d38071561969",
   "metadata": {},
   "outputs": [],
   "source": [
    "f = open('source.txt','r+')\n",
    "new = open('destination.txt', 'w', encoding='windows-1251')\n",
    "for line in f:\n",
    "    new.write(line)\n",
    "f.close()\n",
    "new.close()\n",
    "new = open('destination.txt', 'r')\n",
    "new.close()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 490,
   "id": "946cb235-d611-45f1-93ec-5837cf595b75",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Итого стоимость продуктов составит: ['Яблоки', 'Бананы', 'Апельсины', 'Груши'] 650 рублей\n"
     ]
    }
   ],
   "source": [
    "order={}\n",
    "types=[]\n",
    "with open ('prices.txt', 'r', encoding='utf-8') as f:\n",
    "    for line in f:\n",
    "        types=line.split()\n",
    "        \"\"\"print(types)\n",
    "        print(types[0])\"\"\"\n",
    "        order[types[0]]=types[1:3]\n",
    "result=0\n",
    "for amount, price in order.values():\n",
    "    #print(amount)\n",
    "    #print(price)\n",
    "    value = (int(amount) * int(price))\n",
    "    #print(value)\n",
    "    result+=value\n",
    "print(f\"Итого стоимость продуктов составит: {list(order.keys())} {result} рублей\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 389,
   "id": "7235d37a-4080-4adb-8df3-465b651aab7b",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Число слов в файле - 19\n"
     ]
    }
   ],
   "source": [
    "number=0\n",
    "with open ('text_file.txt', 'r', encoding='utf-8') as f:\n",
    "    for line in f:\n",
    "        words=line.split()\n",
    "        #print(words)\n",
    "        for key in words:\n",
    "            if (key == \"—\"):\n",
    "                #print(words.index(key))\n",
    "                words.pop(words.index(key))\n",
    "        number+=len(words)\n",
    "        #print(number)\n",
    "        #print(words)\n",
    "    print (f\"Число слов в файле - {number}\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 457,
   "id": "d2c9ea21-85ef-4e23-9682-1215de6f1714",
   "metadata": {},
   "outputs": [],
   "source": [
    "with open ('input.txt', 'r', encoding='utf-8') as f:\n",
    "    with open('unique_output.txt', 'w', encoding='utf-8') as unique:\n",
    "        strings=[]\n",
    "        for line in f:\n",
    "            strings.append(line)\n",
    "        a=list(set(strings))\n",
    "        for string in a:\n",
    "            unique.write(string)"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.12.4"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
